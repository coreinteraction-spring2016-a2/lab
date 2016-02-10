# Week 3 Notes

This week we're going to be looking at the `display` and `position` CSS properties – properties you'll be using extensively to customize the layout of your sites.

## Display

Four of the values you'll use most commonly for the `display` property are `none`, `block`, `inline-block`, and `inline`. 

Here they all are in use at once*

```css
.overloaded-box {
	display: none;
	display: block;
	display: inline;
	display: inline-block;
}
```

*There's no reason you would actually write this code

### None

An element that has `display: none` applied to it is not rendered at all. It is invisible, does not take up space on the page, and does not respond to user interaction.

### Block

Block elements:

* Start on a new line
* Expand to fill available width by default
* Respond to `width` and `height` properties
* Respond to vertical and horizontal `padding` and `margin`

### Inline

Inline elements:

* Do not start on a new line
* Expand to accomodate their content
* Do not respond to `width` or `height` properties
* Respond to horizontal but not vertical `margin`
* Vertical padding is displayed, but does not take up space

### Inline Block

Inline block elements are like inline elements except they:

* Respond to `width` and properties
* Respond to vertical and horizontal `padding` and `margin`

[Here's an example of all four values in use](https://jsbin.com/sevonoj/1/edit?html,css,output)

## Position

By default, elements flow one after another down the page, laid out vertically or horizontally depending on their `display` property. The `position` property allows you to use different logics to lay them out instead.

The `position` property is often paired with the `top`, `bottom`, `left`, and `right` properties. 

Here's an example of how it looks:

```css
.fixed-element {
	position: fixed;
	top: 10%;
	left: 10%;
}
```
The values of position that we'll look at today are `relative`, `fixed`, and `absolute`.

### Relative

`position: relative` allow you to adjust the position of an element relative to where it would fall naturally.

So, given the CSS below:

```css
.offset-element {
	position: relative;
	top: 10px;
}
```

An element with the class `offset-element` would be positioned 10 pixels below (10 pixels from the top) where it would fall naturally.

[See live demo](https://jsbin.com/minohu/1/edit?html,css,output)

### Absolute

`position: absolute` elements are positioned relative to their closest parent whose position is `relative`, `fixed`, or `absolute`. If none exist, they are positioned relative to the document.

So, given the following CSS:

```css
.container-element {
	position: relative;
}

.inner-element {
	position: absolute;
	top: 10px;
	left: 10px;
}
```

And this HTML

```html
<div class="container-element">
	<div class="inner-element"></div>
</div>
```

The inner `div` would be positioned 10 pixels from the top and 10 pixels from the left of the container `div`.

[See live demo](https://jsbin.com/qawubi/2/edit?html,css,output)

#### Filling a parent element

One neat thing you can do with `position: absolute` is set all four offset properties (again, `top`, `bottom`, `left`, and `right`) to create an element that fills all or most of its parent container.

For example, given the CSS:

```css
.outer-element {
	position: relative;
}

.inner-element {
	position: absolute;
	top: 10px;
	bottom: 10px;
	left: 10px;
	right: 10px;	
}
```

And the HTML:

```html
<div class="outer-element">
	<div class="inner-element"></div>
</div>
```

The inner element would fill the outer element with a 10 pixel offset around its edges.

[See live](https://jsbin.com/kopavo/1/edit?html,css,output)

#### Centering with position: absolute

It's possible to center elements of known width and height using `position: absolute`.

Here's an example. Given this CSS:

```css
.container-element {
	position: relative;
	width: 600px;
	height: 600px;
}

.inner-element {
	position: absolute;
	width: 50px;
	height: 50px;
	top: 50%;
	left: 50%;
	margin-top: -25px;
	margin-left: -25px;
}
```

and this HTML:

```html
<div class="container-element">
	<div class="inner-element"></div>
</div>
```

The inner element would be centered inside its container. Note that the negative horizontal margin is half of the element's width, and the negative vertical margin is half of its height.

[See live example](https://jsbin.com/ripaduj/1/edit?html,css,output)

### Fixed

`position: fixed` elements are positioned relative to window. They stay in place regardless of scroll position on the page.

Given this CSS:

```css
.fixed-element {
	position: fixed;
	top: 15px;
	left: 15px;
}
```

And this HTML:

```html
<div class="fixed-element"></div>
```

The element with the class `fixed-element` will always stay 15 pixels from the top and left sides of the window.

[See live demo](https://jsbin.com/keyaki/1/edit?html,css,output)

### Z-index

Usually, elements that appear later in your HTML will sit on top of elements that come earlier, but you can use the CSS property `z-index` to change that. `z-index` only works when applied to elements of position `relative`, `absolute`, or `fixed`.

Given this CSS:

```css
.example-element {
	position: absolute;
	top: 0;
	left: 0;
}

.top {
	z-index: 1;
}
```

And this HTML:

```html
<div class="example-element top"></div>
<div class="example-element"></div>
```

The first element will sit on top of the second.

[See live example](https://jsbin.com/loyape/1/edit?html,css,output)

## Random CSS

### Border radius

The `border-radius` property allows you to round the corners of elements. If you use a high enough value, you can create circles and ellipses.

Here's how it looks in CSS

```
.rounded-corner-element {
	border-radius: 10px;
}
```

A common trick is using `border-radius: 50%;` to create a circular or ellipsoidal element.

[See live example](https://jsbin.com/fehakan/1/edit?html,css,output)
 
## Further reading

[http://alistapart.com/article/css-positioning-101](http://alistapart.com/article/css-positioning-101)  
[http://learn.shayhowe.com/html-css/positioning-content/](http://learn.shayhowe.com/html-css/positioning-content/)
