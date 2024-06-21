# Value vs Reference

Primitive types are data types that are passed in by value.  Meaning the variable that you set has the actual value.  

Arrays, objects, and functions are passed in by reference.  The variable for these data structures actually stores the memory address for the value and not the value itself.
The reason for this is because with the primitive types we know how much data is needed to store the value and for arrays, object, and functions can vary in length.  

This is important to know for when passing variables in a function.

```
let a = 5;

function addTwo(num) {
    num = num + 2;
    console.log(num);
    // console will print 7
}

console.log(a);
// console will print 5
```
Since a is a number which is a primitive type the value is store, so when we pass it into the function the value is passed in.  We can change the value in the function and it doesn't affect the variable outside the function.

But now if we do it with an array
```
let numArr = [1, 2, 3];

function addTwo(arr) {
    for(let i = 0; i < arr.length; i++) {
        arr[i] += 2;
    }
}

console.log(numArr);
// will print [3, 4, 5]
```

Since the array variable is actually a reference(memory address to the values) operations in the function now affects the array outside the function.

