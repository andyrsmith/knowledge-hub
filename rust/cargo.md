# Cargo

Cargo is Rust's build and package manager system.  We can use cargo to start a new project and build our application.

## Create a new project

The new argument is used to create a new folder with the starting files you need to run the Rust program.

```
cargo new hello
```

This command will create a new directory called hello.  In that directory will include the following.

- Cargo.toml : This file includes the name and version of your program and any dependencies that is needed to be installed.
- src/main.rs : This is starting source code for your application.  To start it is just the main function followed by a statement to print text to the console.
- .git : creates a git repository for your application.
- .gitignore : contains what files to ignore in our commits.  To start there is just the target directory.


## Run the application

The run argument will build and then run.  Any dependencies that needs to be installed before building will be downloaded first.

```
cargo run
```

