# Colors

How Colors can be applied in CSS

## By name

Some colors can be applied by name.  Currently there are about 140 color names that can be applied to most browser, but this could always change depending on future browser support.

```
p {
    color: red;
}
```

List of some of the color names. https://www.w3schools.com/cssref/css_colors.php

## Hexadecimal

Refers to a 6 digit hexadecimal value for colors. Use hexadecimal by starting it with a # sign.  The first 2 digit in stands for the amount of red color, next 2 for the green, and last 2 for the blue.

```
p {
    color: #ff0000;
}
```

To add transparency to the color with hexadecimal add 2 more digits at the end.

Hexadecimal numbering starts with 0 and ends with the letter f.

## RGB

Allows you to specifiy the red green and blue value for the color using number 1 - 255 or percentage.

```
p {
    color: rgb(120, 0, 120);
}
```

Add alpha value by after the blue value by adding / and number

```
p {
    color: rgb(120, 0, 120 / .2);
```

## HSL

Use the hsl color function to specfiy the hue, saturation, and lightness

```
p {
    color: hsl(50, 70%, 65%);
}
```

Also include alpha channel by this

```
p {
    color: hsl(50, 70%, 65% / .7);
}
```
