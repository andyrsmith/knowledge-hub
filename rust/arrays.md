# Arrays

Two rules for arrays in rust.
- The items in the array must be the same type.
- The array cannot change size.


## Declare an array

Use the let keyword like you would with any other variable.

```
let vegatables : [&str;3] = [ "carrot", "potato", "celery"];
```

or you don't need need to put in type or length.  Rust can infer that.

```
let vegatables = [ "carrot", "potato", "celery"];
```

or can declare it and assign later

```
let vegatables : [&str;3];
vegatables = [ "carrot", "potato", "celery"];
```

## Iterating over an array

Use the for in syntax is the safe way to iterate over the array.

```
for vegatable in &vegatables {
    println!("There is an {}", vegatable);
}
```

