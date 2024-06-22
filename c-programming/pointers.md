# C Pointers

In c you can create a variable that just points to a memory address

## What is a memory address

This is a place in your computer memory where the value is store.

This could look like this table

| Address   | Value |
| 0x5000000 | 3     |
| 0x5000001 | 5     |

The 0x means that we are representing the address in hexadecimal  notation

## Pointer 

So we could use a place in memory that points to a different address

| Address   | Value |
| 0x5000000 | 3     |
| 0x5000001 | 5     |
| 0x5000002 | 0x50000000 |

The last address just points to the first so that we can use the

##  How to delcare a pointer in C

```
int x = 3; 
int *p = &x;
```

The * symbol here declares the variable a pointer and the & symbol signals that we will use the address of the variable x
On the left when declaring a pointer it doesn't matter if there is white space or no white space

```
int * p = &x;
int* p = &x;
```

Both are valid

## Reasons to use pointers

- To pass variables by reference into a function.  This way you can update the variables without have to make a copy of the variable and return the value back
- Use dynamic memory.  Isn't of being fixed to a certain length you can determine memory at runtime.