# Javascript CallStack

## What is the call stack

The Javascript call stack is a data structure that is used for function calls.  It is a LIFO (Last in First Out) meaning that the last function call that was added to the stack will be the first function call removed from the stack.

## How does it work

Since javascript is singled threaded it only has one call stack.

When your code is being execated and it finds a function call that is added to the stack.  If that has a function call has another function call inside it then that function call is placed on top of the first function call. The function call that is on top is first removed after the once it returns.  

Call stacks don't have an infinite size and an error maximum call stack exceeded.
