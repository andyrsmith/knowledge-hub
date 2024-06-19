# Linked List

A linked list is a data structure that is consisted of nodes that are scrattered across a computers memory.  This is different from an array as an array needs to have a block of data that is next to each other. 

The advantage of this over an array is that you don't need to allocated all of the memory all at once, you can add data as you need to.

## Node

The node is the data object.  It will contain the data which you need to store, and a pointer to the next node.

An example of this in C would be:
```
typedef struct node
{
    char *name;
    int age;
    struct node *next;
} node;
```

The example stores someone's name and age, but we can store any number of data.  The pointer to the next node which in the example is called next is curical as without it we don't have a linked list.

## First Node

Once we have a node object we need to store a reference to the first object in the Linked List

In C this could just be a pointer to the first node
```
node *first_node = n;
```

First node needs to be stored in a variable and then will be able to access each other node from there.

## Reading and Searching data

In order to read or search for data in a linked list we must transverse the entire list starting with the first node then proceed to the next node and so on.

The best case is that the node we want is the first node, but worst case is that it could be at the end.

Big O Notion: O(N)

## Insertion

Inserting data is where a linked list has an advantage.  

To insert we just create the new node.  The new node's next node would be the current first node and then the new node would become the new first node.

Big O Notion: O(1)

Inserting anywhere else does require us to transverse the list to the spot where we need to insert the data.  Once we find the spot to insert we need to update the previous node's next to be the new node and the new node's next would have to the what use to be the previous nodes next node. 

Since we have to transverse what could be the entire linked list the this would be a Big O of (N)

## Deletion

Similar to insertion deleting at the beginning is said to have a Big O(1).  All that is needed is to update the first node to be the deleted node's next.

Deleting anywhere else and we again have to travel through each node to get to the node to be deleted.

So again this could be O(N)
