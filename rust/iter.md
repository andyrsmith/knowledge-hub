# Iter

Iterators allows you to manipulate data in a list of data like an array.

Call it on an array with .iter()

```
item_list.iter()
```

Use the iterator in a function chain.  One method is the find method.

## Find

Find locates data that you specify.

```
let found_item = item_list()
    .iter()
    .find(|item| item.name == some_name)
```

Find returns an Option type.  Option type either has data or none.

Use match with option type. [match](match.md)
