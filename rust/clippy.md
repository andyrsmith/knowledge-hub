# Clippy

Clippy is a tool that is included in Rust.  It will provide you with a list of warnings about your code. 

Run the command 

```
cargo clippy
```

If there are any suggestion on how to improve your code it will provide them in the output.

If you want clippy to provide you with more warnings then add this to the top of your rust file

```
#![warn(clippy::all, clippy::pedantic)]
```

There are other options that you can give clippy. You can see them here
[https://github.com/rust-lang/rust-clippy](Github Clippy)
