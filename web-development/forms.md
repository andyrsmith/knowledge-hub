# Forms

To create a form for the web use the <form> tag. Within that form tag there is label, input, and submit button.

```
<form>
    <label for="name">Name</label>
    <input type="text" id="name" name="name">
    <input type="submit" value"Submit">
</form>
```

When hitting the submit button the form will make a get request on the exact same url that you are at except you will see an ?name="" added to the end.

From forms you are able to do a get request or a post request.  Change the form to a post by using the method attribute.
```
<form method="post">
```

By using the post method the params will show up in the body of the request instead of the params of the url.  Use post when the data enter in the form should not show up in the url.  If data is like that of a search form then get is fine to use.  That way the user can come back to that exact user later by going back in their browser history.

The action attribute can be set in the form tag to specify the url in which the request is sent to when the submit button is pressed.
```
<form action="http://localhost:8080/api/v1/names" method="post">
```

When the form button is submitted it will send a post request to the url http://localhost:8080/api/v1/names.

Using this we can create a form that make a search on Google.com

```
<form action="https://www.google.com/search">
    <label for="search">Search</label>
    <input type="text" id="search" name="q">
    <input type="submit" value"Submit">
</form>
```
q is the param that google is looking for when creating the query so name will equal q.

## Inputs

In the above example an text field input was created and was paired with a label.  The label has a for attribute of name.  The value in name should match the ID of the input that it represents. 

The name attribute will be how the data is sent when the form is submitted.  If the form using the get request then after we will submit the form we will see the value of the name field in the url params.

### Text

A single line text value. Type = text

```
<label for="animal">Animal</label>
<input type="text" id="animal">
```

### Textbox

A multiple line text value.  Uses the html tag of textarea.

```
<label for="story">Enter your story</label>
<textarea id="story" name="story">
Default text
</textarea>
```

### radio

A radio check is typically done in a group of options where only one of the options can be selected at a time.

```
<fieldset>
    <legend>Pick an option:</legend>
    <input type="radio" name="pet" id="petchoice1" value="dog">
    <label for="petchoice1">Dog</label>
    <input type="radio" name="pet" id="petchoice2" value="cat">
    <label for="petchoice2">Cat</label>
    <input type="radio" name="pet" id="petchoice3" value="fish">
    <label for="petchoice3">Fish</label>
</fieldset>
```

### checkbox

A checkbox can be used with multiple options can be selected.

```
<fieldset>
    <legend>Pick an option:</legend>
    <input type="checkbox" name="dog" id="petchoice1">
    <label for="petchoice1">Dog</label>
    <input type="checkbox" name="cat" id="petchoice2">
    <label for="petchoice2">Cat</label>
    <input type="checkbox" name="fish" id="petchoice3">
    <label for="petchoice3">Fish</label>
</fieldset>
```
With a checkbox we can select multiple pets.


### others

Other input types that we can put in are date, password, tel, search, and many more.

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input

## Fieldset

Used to group similar form controls.

## Validation

### required

Adding required as an attribute to one of the input fields will force a user to enter data for that field.

```
<input required type="text" name="firstName">
```

### Pattern

Using the pattern attribute will force the user to enter data the obeys the pattern rule that you set.

```
<input required pattern="[A-Z]" name="firstName">
```

In this example a user can only use uppercase letters.

### Styling forms for errors

Use the invalid pseudo-class to set the border as red when invalid or no data is entered.

```
input:invalid {
    border: 2px solid red;
}
```

### Set an error message for forms

Make an message appear when user enters invalid data.

```
const input = document.querySelector('[name="firstName"]');

input.addEventListener('invalid', () => {
    input.setCustomValidity('Failed to enter a first name');
});
```

That message will appear when field becomes invalid.

## Accessibility

### for attribute

Labels have a attribute for this must match the id of that input.  This ties the label and the input togather, which when the screen reader focuses on the input it will read out the label.

```
<label for="firstName">
<input type="text" id="firstName">
```

### Aria-describedby

Putting an aria-describedby on the input that connects to the id of an error message will help the screen reader connect that error to the input.

```
<input type="text" id="firstName" aria-describedby="nameError" required>
<span id="nameError">Must include name</span>
```

### Other tips

Only disable the button while the form is submitting.  If the user hits the submit form and the form isn't valid then trigger errors.
