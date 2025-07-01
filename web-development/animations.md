# Animations

Animation property is use to create animations of html elements.  It requires a animations property on that element and then keyframe property.

There are 2 ways to define animations.


```
div {
    animation: sunrise 3s linear 1s infinite alternate;
}
```

or 

```
div {
    animation-name: sunrise;
    animation-duration: 3s;
    animation-timing-function: linear;
    animation-delay: 1s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    animation-fill-mode: none;
    animation-play-state: running;
    animation-composition: add;
}
```

## Animation properties

    - animation-name: The name given.  This is how you reference
    - animation-duration: Length of time in each animation cycle
    - animation-timing-funcion: acceleration curve of the animation
    - animation-delay: time before animation starts
    - animation-direction: If animation should go forward, backwards, or alternates
    - animation-iteration-count: how many times animation should work
    - animation-fill-mode: defines how style is applied before and after run
    - animation-play-state: controls whether to pause or play animation
    - animation-composition: controls how animation behavior when multiple animations are in affect.  Not available in short hand notation.

## Keyframes

Keyframes define what the animation does.  The name will be the same given in the animation property for your element.

```
@keyframes sunrise {
    from {
        transform: translateY(110vh);
    }

    to {
        transform: translateY(0);
    }
}
```

After specifying @keyframes then you put in the name of the animation.

The from is the starting point and the to is the ending point.  So the animation will start a 110vh and go to 0vh, and since we set as infinite and alternate the animation will go on forever moving up and down.

Instead of to and from we can use percentages to define mutliple points of transition

```
@keyframes sunrise {
    25%
    50%{
        transform: translateY(110vh);
    }

    50%
    75% {
        transform: translateY(25vh);
    }

    75%
    100% {
        transform: translateY(0);
    }
}
```
