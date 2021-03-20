# Linked Lists
[Home](../Class-Readings)

## What is a Linked List
A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

There are two types of Linked List - Singly and Doubly.

## Terminology:
### Linked List -
A data structure that contains nodes that links/points to the next node in the list.

**Singly** - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.

**Doubly** - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.

**Node** - Each node contains the data for each link. Next - Each node contains a property called Next. This property contains the reference to the next node.

**Head** - The Head is a reference type of type Node to the first node in a linked list.

**Current** - The Current reference is a reference type of type Node that is currently being looked at.

[Reference](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

---

## Traversal
---
When traversing a linked list, you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing. The Next property is exceptionally important because it will lead us where the next node is and allow us to extract the data appropriately.

The best way to approach a traversal is through the use of a while() loop. This allows us to continually check that the Next node in the list is not null. If we accidentally end up trying to traverse on a node that is null, a NullReferenceException gets thrown and our program will crash/end.

When traversing through a linked list, the Current node is the most helpful. The Current will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end.

## Example
Let’s put a use case on our traversal - to check whether or not our LinkedList Includes a specific value.

The pseudo-code for an Includes is as below:

    ALGORTIHM Includes (value)
    // INPUT <-- integer value
    // OUTPUT <-- boolean

        Current <-- Head

	        WHILE Current is not NULL
	            IF Current.Value is equal to value
		            return TRUE
  
        Current <-- Current.Next
  
    return FALSE

What exactly is taking place:

1. We are first setting Current to the Head to guarantee we are starting from the beginning. (Remember that Head is always the first node in a Linked List)

2. We create a while loop. This loop will only run if the node that Current is pointing to is not null. This also means we can guarantee that we are still looking at a Node while the loop is running.

3. Once we are in the while loop, we are checking if the value of the current node is equal to the value we are looking for. Given the logic, if that condition is true, then we have found the value we were looking for, so we return true.

4. If the Current node does not contain the value we are looking for, we then must move Current to the next node that is being referenced. Again, because the condition of this while loop is to only run if we are still at a node, we can safely traverse to the next node without fear of getting a NullReferenceException.

5. At this point, the while loop is re-evaluated. Step 3 & 4 will continue until Current reaches the end of the LinkedList. We will know we are at the last node in the linked list because the current node will be null. Once this condition becomes true, the while loop breaks, and we now know that we are at the end.

6. Once we hit the end, we know that we did not find the value and return true at any point, so the value is not in the LinkedList. We return false.

[What is a Linked List, Anyway - Part 1](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)

[What is a Linked List, Anyway - Part 2](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)

## Features
---
- The fundamental difference between arrays and linked lists is that arrays are static data structures, while linked lists are dynamic data structures.

- A static data structure needs all of its resources to be allocated when the structure is created. Always needs a given size and amount of memory.

- A dynamic data structure can shrink and grow in memory. It doesn’t need a set amount of memory to be allocated in order to exist, and its size and shape can change, and the amount of memory it needs can change as well.

## Insertions
---
- Factor in the BigO when thinking about this.

- When inserting at the head, the new node has to link to the current node and then the head will link to it. Since it is indepedent of the size of the linked lists, the tiem and space factor is O(1)

- But when linking to the end of the list, you have to traverse through the entire breadth of the linked lists. Since this can vary based on the size, the time factor is O(n)

- When adding to the end of the list, the new node has to connect to null first. Now there are two nodes connect to null. The the current node with the next value has null, will then attach to the new node and make it part of the linked chain.

- When adding a new node to the middle of the list, use a while loop to loop through the linked lists until you reach the node with next value as the value we want to AddBefore. Then connect the new node to the next node, and then change the current node's next value to the new node. This will insert the new node into the link. Since it is dependent on the length of the link, the BigO is O(n)

