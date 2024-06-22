# Arrays

An array is a list of data starting that starts at a particular memory address and takes up the next series of memory addresses that was defined by a program.

If an array has five elements and array memory address starts at 1001, then the other four memory address would be 1002, 1003, 1004, 1005.  The memory address are always in order.  You would never see an array with an location at 1005 and then the next element at 1007.  That just doesn't happen in arrays.  If array needs to handle more data then orginally allociated that all of the data would have to be copied to a new location.

## Reading from an Array

Typically if you want to read data from the array you reference the variable in which you defined the array with an index number starting at zero.

```
let arr = [1, 2, 3]

console.log(arr[0])
//will print 1 the first element
```

The variable for the array will most likely store the memory address of the first element and with the index value the program can add that to starting memory address to quickly get any value in the array in one step.  

Reading from an array in Big O is O(1)

## Searching

In an array which is unsorted in order to find the value in which you are looking for you might have to look through each item in the array.  So it could be the first item in the array or it could be the last item in the array.

The worst case in searching is O(N).

If the array is sorted it is possible to have a faster time the O(N), like using binary search.

## Insertion

If inserting at the end of an array and if there is still room in the array(allocated more memory than currently using) then inserting will take just one step.  If inserting somewhere else other than the end, then the data in the array will have to move over one space to make room for the item you wish to insert. 

If array is full then a new array will need to be allocated with more space and then each data value will need to be move to it's new data location.

Inserting at the end has a Big O of O(1)
Inserting at anywhere else has a Big O of O(n+1).  


## Deleting

Like insertion deleting from the end is rather simple, but deleting from anywhere else requires the array to shift values from left to right to fill in the deleted element.

Worst case Big O is O(n)