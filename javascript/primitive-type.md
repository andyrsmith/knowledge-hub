# Primitive Types

## A little about Javascript variables

Javascript is a dynamically and weakly typed language.  Dynamic means that a variable can be any type.  Weak typed is that it allows conversion of two variables that have different types without throwing an error.  

So if you have one variable that is "Hey" and another that is a number 1, and try to add them then you get "Hey1"

Primitive types do not have methods that can be called on them.

## Javascript Primitive Types

Anything else that is not in this list is an Object, including functions.

Non primitive types are Objects and Arrays.

### null

Null type has only one value, which is null. This is a variable with no value.  If you need to reset a variable to a nothing value use null instead of undefined.

### undefined

Undefined type has only one value, wich is undefined.

A variable that is declared, but not initialized will return undefined.

Ex.

```
let a;
console.log(a) //will print undefined
```

Since this is the case if you need to reset a variable to a nothing value best use null. If variable is reset to undefined you may get confused if variable has been initialized in the first place.

A function with no return statement will return undefined.

### boolean

This has 2 values.  True/False

These are used in conditional operations, like if/else statements.

### Number

This stores a double precision 64 bit value.  It can store a floating point number between 2^-1074 - 2^1024 and integer -(2^53-1) and 2^53-1.  

A number that falls outside the max range will return Infinity and a number that falls below 0.


### BigInt

BigInt type can store numbers that are outside the safe range of a normal number.

### String

This type is represents text on the screen.  
```
let text = "Hi";
```

The value needs to be surrounded by quotes. Either single or double quotes.

You are able to add other strings to the value or since Javascript is a weakly typed language a number value as well.

Strings are represented by a sequence of 16 bit unsigned integer value.  Meaning that each character in a string are represented by 16 bits or 2 bytes of data. 

### Symbol

Symbol is a unique and immutable value.  These can be used a key to an object or some other unique property key.