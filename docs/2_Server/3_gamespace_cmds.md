---
sidebar_position: 3
---
# Gamespace Commands

The **Gamespace** is the virtual architecture of the Space Merchant universe. It is structured as a **Tree Graph**, allowing for a nested, hierarchical environment.

### The Hierarchy Model
* **Mother Node:** The "Root" of the universe. All other nodes descend from here.
* **General Nodes:** Structural nodes representing regions, sectors, or star systems. They act as "branches" to organize the space.
* **Elemental Nodes:** The "Leaves" of the tree. These are the only nodes that represent physical locations where **Markets** and **Containers** can exist.

---

## 🏗 Node Management

Use the following commands while in the **Configuration State** to build or expand your universe.

### Create General Node
Use this to define a new region or sector. General nodes serve as containers for other nodes but do not hold markets themselves.
```
CREATE_GENERAL_NODE <node_name> <parent_node_name> <x_coordinate> <y_coordinate>
```

### Create Elemental Node
To create a new elemental node, use this command. Similar to creating general nodes, you have to add the capacity parameter to specify how much this node can have built in.
```
CREATE_ELEMENTAL_NODE <node_name> <parent_node_name> <x_coordinate> <y_coordinate> <capacity>
```
**capacity**: A numerical value representing the maximum buildable/storable volume within this location.

Note: Elemental nodes must be attached to a General Node or the Mother Node to be reachable.

🛰 Spatial Logic Tip

Think of General Nodes as Sectors and Elemental Nodes as Stations. Players navigate through the General Nodes to reach the Elemental Nodes where the actual trading happens.