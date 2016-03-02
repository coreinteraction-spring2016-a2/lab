# Week 6 Notes

## Semantic markup tags

Using semantic tags is an important part of making your site accessible. While it's possible to replicate the display of the tags below using plain 'ol divs and css, using semantic tags makes it easier for **computers** to understand the structure of your webpage. People who have loss of vision often use screen readers to access websites – computer programs that read from and describe websites. Using semantic tags makes it simpler for the program to parse and describe your site to its users.

Tag | Use
--- | ---
`<h1></h1>`<br>`<h2></h2>`<br>`<h3></h3>`<br>`<h4></h4>`<br>`<h5></h5>`<br>`<h6></h6>` | Headings. `h1` is the most important (and biggest). `h6` is the smallest
`<p></p>` | A paragraph. Default style includes vertical margin
`<br>` | Adds a line break in inline content
`<b></b>` | Makes contained text bold by default
`<i></i>` | Makes contained text italic by default
`<ul></ul>` | An unordered list. Items will be bulleted by default. Contains many `li`s
`<ol></ol>` | An ordered list. Items will be numbered by default. Contains many `li`s
`<li></li>` | A list item. Belongs to an `ol` or `ul`

[Live semantic markup example](https://jsbin.com/gikoxi/edit?html,output)

## Form tags

Forms allow you to solicit input from your site's users. You'll most commonly use the tags below to construct your forms.

Tag | Use
--- | ---
`<form></form>` | Wrapper for form content
`<label></label>` | Label (usually for a specific input)
`<input>` | A generic input, can be of many different types (see below)
`<select></select>` | Specialized input that allows the user to select an item from a dropdown. Contains many `options`
`<option></option>` | An option contained by a `select` element
`<textarea></textarea>` | Specialized input used for multiline text

### Inputs

`input` is a very versatile element. Changing an `input`'s  type attribute changes how it displays and the type of data it's optimized for. 

Here are some of the most common `type`s:

Type | Display
--- | ---------
text | Simple, single line text input
password | Password input (obscures entered text with circles)
radio | Radio button
checkbox | Simple checkbox
button | Simple button

Another attribute you'll work with a lot when using inputs is `value`, which allows you to set the initial value of an input when the page is loaded. It's important to note that `value` is distinct from `placeholder`, an input attribute that allows you to set text to display when a text input is empty.

Here's the HTML for a text input with a placeholder and a value:

```html
<input type="text" value="Hello!" placeholder="Enter your message here">
```

[Live inputs example](https://jsbin.com/hilaxi/13/edit?html,css,output)

### Javascript and inputs

Getting the value of a text input is simple using jQuery.

```javascript
$('input').val()
```

Since you may have multiple inputs with the same tag name, same classes, etc., it can make sense to set `name` attributes on your elements and use those to select them. Here's how inputs with name attributes look:

```html
<input type="text" name="firstName">
<input type="text" name="lastName">
```

And here's how you'd get their values in javascript:

```javascript
var firstName = $('input[name=firstName]').val();
var lastName = $('input[name=lastName]').val();
```

This also works for getting the values of `select` and `textarea` elements.

[Live example](https://jsbin.com/seqobo/3/edit?html,js,output)

#### Listening for changes

Often, you'll want to change something on your page when the value of an input element changes. jQuery's `change` function works well for this. It functions very similarly to the way the `click` function does.

Here's how it looks:

```javascript
$('input').change(function () {
	var newValue = $(this).val();
});
```

[Live example](https://jsbin.com/yucavuk/3/edit?html,js,output)

