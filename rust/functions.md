# Functions

Functions can be used to break up your code into smaller pieces.  

## Create Function

Use the fn to declare a function.

```
fn enter_name() -> String {
    let mut name = String::new();

    stdin()
        .read_line(&mut name)
        .expect("Failed to read line");

    name
}
```

In the () you are able to pass in any agruments you wish, which here we have none.  The -> String denotes the return type of the function.  For this function we are returning a String, but could return any variable type like boolean, int, or even void (none).

When specifing what to return just put it on a single line without the semi-colon. 
