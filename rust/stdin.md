# Stdin

Stdin provides functions like read_line that you are able to import into your program.

## Read_line

Read_line is used to read input from the user. It takes a mutable reference to a variable in which to store the input in.

```
stdin().read_line(&mut name);
```

Whatever the user enters in the terminal is stored in the variable name.

- add link to borrowing

It is good to chain an expect to the end of read_line in case that method encounters an error.

```
stdin()
    .read_line(&mut name)
    .expect("Failed to read line");
```

- add link to error handling
