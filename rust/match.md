# Match

Using Match we can work with Option types by telling the code to do something if it finds data and do something else if we don't find data.

```
match found_item {
    Some(item) => println!("You found my favorite item, {}!", item.name),
    None => println!("You didn't find my favorite item, now I am sad.")
}
```

This will print one thing is item is found and another if it is not.

