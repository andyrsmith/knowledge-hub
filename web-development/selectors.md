# CSS Selectors

## Basic Selector

Select a html element

```
h1 {
    font-size: 16px;
}
```

Select a class with using the dot in front of class name and # in front of ID.

Select multiple elements at the same time with a comma

```
h1, h2 {
    font-size: 16px;
}
```

Universal selector is the * this applies css properties to all elements.  Often done to apply a CSS reset.

``` 
* {
    margin: 0;
}
```

Select element within another element like a span within a paragraph tag

```
p span {
    font-size: 8px;
}
```

