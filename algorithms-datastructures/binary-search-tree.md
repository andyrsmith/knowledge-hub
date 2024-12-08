# Binary Search Tree

A Binary Search Tree is where each node has zero, one, or two children. 

Each node can have up to one left and one right child node.

The left node has a value less then the value of the current node.

The right node has a value greater than the value the current node.

## Searching

First compare the search value with that of the root nodes value.

If same value then done searching

If the value is less than the root node then look at the value from the left child.
If value is greater than the left child value, then look to the right child.

Repeat these steps for each level until the result  is found or at the end of the list.

The efficiency is O(log N) because each level we go down in searching the amount that we have remaining to search is cut in half.  This is the assuming that the tree is balanced. If the tree is imbalanced then it would have a O(N).

*log n is the reverse of n^2

## Insertion

When inserting a new value we start at the root node, then compare the root value with the value we want to insert.  
If the new value less then root we move to the left, if the value is greater than we move to the right.
We repeat that process until we get to a node without children 
Then insert that value under that node either left or right

The efficiency is said to have O(log n) + 1 for the insertion.   Or just said O(log n) because we drop the constant.

## imbalanced tree

If a tree has more nodes on one side then the other the tree is said to be imbalanced.  The worst case in that scenario is O(N)

## Deletion

Deletion first requires a search to find the node value that is to be deleted.

If the node found has no children then the node can be remove as a left or right value of the parent.

If the node has one child then that child node becomes a child to the node above the deleted one.

If there are 2 child nodes then the least valued node that is of greater value then deleted node take the place of the deleted node.

In other words first travel to the right node, then as long as there is a left node keep traveling to the left node until there is one anymore.  This will be the value that takes it's place.  

If you traveled right and there is no left then that right node will be the node to use as a replacement.  If the node has a right but no left, then the right node will become a left node.
	

## Traversal

To traverse the binary search tree you.

Call the method recursively on the left child
print the current node

call the method recursively on the right child

If no node the return
