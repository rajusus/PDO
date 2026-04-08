---
sidebar_position: 3
---
# Gamespace commands
Gamespace is the virtual enviroment of the game. It is composed of a tree graph with one node as the mother node and its lesser child nodes representing smaller domains/regions. The nodes least nodes are called elemental nodes and represent the individual locations where markets and containers can be located.

### Create General Node
When you want to create a new general node, you can use this command. You will have to specify the new node's name, tha name of its parent and the x and y coordinates.
```
CREATE_GENERAL_NODE <node_name> <parent_node_name> <x_coordinate> <y_coordinate>
```

### Create Elemental Node
To create a new elemental node, use this command. Similar to creating general nodes, you have to add the capacity parameter to specify how much this node can have built in.
```
CREATE_ELEMENTAL_NODE <node_name> <parent_node_name> <x_coordinate> <y_coordinate> <capacity>
```