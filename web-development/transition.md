# Transitions

Transitions will control what properties and how it will transition on a psuedo class.

Transitions is shorthand and contains the following properites

```
transition: property duration timing-function delay
```

At the minimum it must include a property.  If only property is included then 0s will be the duration and delay and no timing function will be in affect.

- transition-property: This is the property that will transition to
- transition-duration: This is how many seconds or milliseconds 
- transition-timing-function: Speed curve of the transition
- transition-delay: When the transition will start


Example

```
div {
    transition: background-color 5s ease-in 500ms;
}

div:hover {
    background-color: red;
}
```

Whatever property is specified in the transition then it must be used in a psuedo class for that element.

Transition-timing-function
(https://www.w3schools.com/cssref/css3_pr_transition-timing-function.php)[https://www.w3schools.com/cssref/css3_pr_transition-timing-function.php]
