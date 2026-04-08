---
sidebar_position: 2
---
# Server States

There are 4 possible states the server can have:
- **Idle**
- **Configuration**
- **Running**
- **Quitting**

Each state has its own keyboard button that will switch the server to it.

## Idle State
Activation key: **i**
When you start a server, it starts up in the *Idle* state. In this state, the server does not do anything except react to client requests and the admin inputs. It will complete client requests, if they are doable, and send other clients updates. But it will not process the simulation.

## Configuration State
Activation key: **c**
In the configuration state, the server admin can manipulate the server's data using commands. While in this state, no new clients can connect to the server and no connected clients can have their requests fullfilled. Once the configuration state ends, the clients will wipe their local data copies and the server will send them the entire new data contents.

When in the configuration state, the admin has to exit the state first before being able to switch to a different state.

## Running State
Activation key: **r**
In this state the server will run the actuall simulation. It will process the data in ticks and send the event package to clients after each tick.

## Quitting
Activation key: **q**
Once the server switches to this state it is not possible to switch to a different one until it is turned off. The server will save all its internal data and shut down.