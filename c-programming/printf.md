# Printf

Printf is a function tha outputs text to the console that is included in stdio.h

## Usage

Must include the following header file

```
#include <stdio.h>
```

Printf is used by calling the function and passing in a string of text that you wish to output.

```
printf("Hello, World\n");
```

This will print Hello, world to the console and the \n will create a line break.

To use a variable in printf a symbol like %d will need to be included in the string followed by a comma, then the variable name like this.

```
printf("Hello, I am %d years old", age);
```

The %d will be used to in place of the integer, other data types have their own specific symbol to use.

- %d : integer
- %c : character
- %f : float
- %s : string
- %p : memory address
- %x : hexademical

Can use muliple variables in the same printf function like so.

```
printf("Hello %s, %d days until your birthday", name, days_left);
```
