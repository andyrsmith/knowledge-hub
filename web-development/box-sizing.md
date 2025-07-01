# Box Sizing

This css property tells the browser how the height and width should be calculated.

```
.some-div {
    box-sizing: content-box;
}
```

- content-box: default behavior.  Padding and border is added after content so if the width of the container is 100px then with the padding and border the container will actually be greater than 100px
- border-box: Padding and border is included in the width so if the container is set to 100px than it will be only 100px.
