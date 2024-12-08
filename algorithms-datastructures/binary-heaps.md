# Binary Heaps

A binary heap is a complete binary tree is where each node( right and left ) is less than the parent called Max Heap or greater than the parent called Min Heap.  Binary Heaps needs to be complete.

Like binary trees each node in a binary heap can only have up to 2 children nodes

Binary heaps are said to be weakly order because when searching for values we have no idea if a node would be to the left or right.  Just if it is greater or less than.  

## Complete

This is when there are no missing nodes expect for the bottom row and only nodes after the current rightmost is missing.  Rightmost node is called the last node.


## Insertion

To insert into a binary heap (Directions are for a Max heap, min heap would look for less than value.)

1. Insert new node next to the right most node.
2. Compare new node with parent node
3. If new node is greater than swap with parent, else stop
4. Repeat step 2 with the new node with the next parent node, and keep repeating until node is less than.


## Deletion

In a Binary Heap the only node that is deleted is the root node. 

The following steps to delete a root node

1. Move the last node where the root node is.
2. Trickle the root node down into its proper place
	1. To trickle down we check compare the new node to the children and swap if the node is smaller then the larger node
3. Repeat step 2 until there are no children or until the node is no longer smaller than the larger of the children node

If we swap with the smaller of the children node than we violate the principle that the parent node is larger than the children node.

## Efficiency of Binary Heaps

For both insertions and deletions the speed is always O(log N)

## Finding the Last Node

Finding the last node is important in inserting and deleting on a binary heap, but there does not seem to be a good way to find the since how do we know which side the last node is on.

Binary heaps are actually arrays.  So the last node is always at the length of the array minus 1.

If binary heaps are arrays how do we tell what the children of the each node is, since it is just a list.

There is a formula to find any child node

left child
(index*2) + 1

right child
(index*2) + 2

parent
(index-1)/2
But with this always round down

## Heaps as Priority Queues

Heaps work well as priority queues because the highest level node is always at the top and as we remove the highest level node the next highest level node rises to the top.
