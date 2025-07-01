# Inside the Component Decorator

The component decorator has the following properties that you can set inside of it.

## Selector

This is where you define how to use the component.  Setting the value to 'user-profile' would mean that you could use this component inside another html template with the following tags.

` <user-profile></user-profile>`

## template or templateUrl

When using template you can write html code or with templateUrl specify a html template to use.

## styles or stylesUrl

Insert CSS styles here using the following

```
styles: [ 'h1: {font-weight: bolde;}']
```
or use stylesUrl to provide a css file to use.

## standalone

TODO