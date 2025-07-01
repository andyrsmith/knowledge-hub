# Media Queries

Media queries are used to apply different css rules to different media types, screen size, orientations, user preferences, and more.

Most commen would be to apply to different screen types like between desktop, tablet or phone.

To use first add @media to the line followed by the rule that you are targeting.

```
@media (max-width: 1200px) {
    p {
        font-size: 10px;
    }
}
```

This would target browser size only up to 1200px.

Can combine multiple rules at the same time like this.

```
@media screen and (max-width: 786px) {
    p {
        font-size: 8px;
    }
}
```

This would target a device screen (phone, tablet, or desktop) and a width up to 786px

Can specify a max and min width also.

```
@media screen and (min-width: 768) and (max-width: 1200px) {
...
}
```

Refer to here for a more complete list of rules that can be applied to media queries. (https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries)[https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries]
