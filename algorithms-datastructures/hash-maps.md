# Maps/Hash Datastructure

A key value pair data structure that is stored in an array

## How is it implemented

There could be a number of ways, but one way is to use an array of linked list to store the data and a hash function to retrieve and add items back in hash.

To insert a value

1. First compute the hash value from the key that is provide
2. Map the hash code to the index.  Something like hash(key) % array_length
3. Store the key and value in this index of a linked list as there could be collisions

To find the value from the key would be a similar process.

## Big O values

Insert and lookup would be most of the time O(1), but with collusion worst case could be O(n)

Hash tables implemented as a binary search tree would have a lookup of O(log n)

## Hash functions

Converts key into integer which will be an index to an array

### Criteria for a good hash functions

- Easy to compute, not an algorithm
- Uniform distribution across hash table not result in clustering
- Few collisions

### Options for dealing with collisions

- separate chaining uses linked list.  In case of collusion can loop through the list until is found.
- Linear probing: if address is taken then data is inserted in next empty slot
- Quadratic probing: similar to Linear but uses is quadratic spacing.
