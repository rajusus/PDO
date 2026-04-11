---
sidebar_position: 2
---

# Server States

The Space Merchant server operates as a **State Machine**. At any given time, the server exists in one of four distinct states, determining how it handles data, network traffic, and simulation logic.

### Quick Reference: State Hotkeys
| State | Key | Function |
| :--- | :---: | :--- |
| **Idle** | `i` | Passive listening and manual updates. |
| **Configuration** | `c` | Administrative data manipulation. |
| **Running** | `r` | Active simulation and tick processing. |
| **Quitting** | `q` | Data persistence and shutdown. |

---

## 💤 Idle State
**Activation Key:** `i`

Upon launch, the server defaults to the **Idle** state.
* **Behavior:** The server maintains connections and fulfills basic client requests (e.g., balance checks) but does **not** advance the game clock.
* **Network:** Clients receive updates if changes occur, but the global economy is effectively "frozen."

## 🛠 Configuration State
**Activation Key:** `c`

This is a privileged mode for administrative overrides.
* **Behavior:** The admin can manipulate internal data structures using console commands. 
* **Lockdown:** To prevent data corruption, **no new clients** can join, and existing clients cannot perform actions.
* **Synchronization:** When exiting this state, the server forces a **global cache wipe** on all connected clients. The server then broadcasts the updated "Master Data" to ensure everyone is synced.
* **Constraint:** You must manually exit the Configuration state before the server will allow a transition to any other state.

## 🚀 Running State
**Activation Key:** `r`

This is the primary gameplay mode.
* **Behavior:** The server processes the simulation in **Ticks**.
* **Events:** After every tick, the server compiles and broadcasts an "Event Package" to all clients, reflecting market shifts, movement, and transaction results.

## 🛑 Quitting State
**Activation Key:** `q`

The shutdown sequence.
* **Behavior:** Once triggered, this state is **irreversible**. The server ceases all network communication, serializes its internal data to the database, and terminates the process.
* **Warning:** Ensure all administrative changes are finalized before pressing `q`.

---

> ### 💡 Pro-Tip: The "Configuration" Sync
> Use the Configuration state sparingly on high-population servers. Since it forces clients to redownload the entire data set upon completion, it can cause a brief spike in network traffic.