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