# Position

This is how elements are aligned within the browser.

```
.some-div {
    position: static;
}
```

## Static

This is the default position of an element and the elements are considered in the normal flow of the document.

## Absolute

Position of this element is set to the closet relative parent element. Can use top, left, right, bottom to position.  Element is considered not in the normal flow of the document.  Able to stack on top of other elements with z-index.

## Relative

Considered in the normal flow of the document and can use top, left, bottom, right to adjust the position.  Other elements will not be adjusted when this element position is changed by those properties.

## Fixed

Position relative to its' viewport.  Content never moves even if scrolled.  Position with top, left, right, and bottom

## Sticky

Position is relative until a certain position set by top, bottom, left, or right is met.  Then the content stays in that viewport no matter if scrolling is happening. If position of top is set to 0 then the content will scroll until position 0 is met then it will stay at position 0 in the viewport.
