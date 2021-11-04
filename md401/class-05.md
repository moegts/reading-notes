# Linked Lists

Linked List is a sequence of Nodes that are connected/linked to each other

## Terminology:-

     - Linked List - A data structure that contains nodes that links/points to the next node in the list.

     - Singly - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.

     - Doubly - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.

     - Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.

     - Next - Each node contains a property called Next. This property contains the reference to the next node.

     - Head - The Head is a reference of type Node to the first node in a linked list.

     - Current - The Current is a reference of type Node to the node that is currently being looked at. When traversing, you create a new Current variable at the Head to guarantee you are starting from the beginning of the linked list.

## Print Out Nodes :-

because we are leveraging our Current node and a while loop to traverse through the existing linked list.
Printing all nodes in a Linked List is similar to the Includes() method.

### Head:-

**Head**: first node in a linked list.

### Current:-

**Current**: type of type Node that is currently being looked at.

### Traversal:-

you are not able to use a foreach or for loop When traversing a linked list,  We depend on the Next value in each node to guide us where the next reference is pointing. The Next property is exceptionally important because it will lead us where the next node is and allow us to extract the data appropriately.

### Big O:-

The **Big** O of time for Includes would be O(n).
This is because, at its worse case, the node we are looking for will be the very last node in the linked list.
n represents the number of nodes in the linked list.

### Adding a Node

- Adding O(1):
you must be careful that all references to each link/node is properly assigned.
Order of operations is extremely important when it comes to working with a Linked List.

- steps to adding Node:

The values passed in as arguments into the Add() method will define what the value of the Node will be.
We can then instantiate the new node that we are adding.