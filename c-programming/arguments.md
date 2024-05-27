# Arguments

C program can accept agruments into the program.  For example a command line application might let you pass in extra characters after program

```
some-program -l -w hello
```

The -l -w and hello could stand for whatever we determine nessary

In the program get the arguments when declaring the main function by

```
int main(int argc, char *argv[])
```

The argument argc would be the number of arguments passed in, and each argument is stored in a character array in argv.



