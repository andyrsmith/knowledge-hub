# Creating Components

There are 2 ways to go about creating a component.  Using the CLI and creating the component file manually.

## Using the CLI

` ng generate component <component-name> `

or 

` ng g c <component-name> `

## Creating the file Manually

create a file called <component-name>.component.ts

Inside the file use the component decorator before the class declaration

```
@component({
    selector: 'user-profile',
    template: '<h1>User Profile</h1>',
    styles: ['h1 { font-weight: bold;}']
})
export class UserProfile {}
```
[Understanding Component properties](inside-component-decorator.md)
