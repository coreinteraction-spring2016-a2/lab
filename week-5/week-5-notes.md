# Week 5 notes

## Images

You can use the `img` tag to include an image on your page. `img` works very similarly to `script`. Here's what it looks like in use:

```html
<img src="glob.jpg">
```

[Live example](https://jsbin.com/coyedu/edit?html,css,output)

## Flexbox

Flexbox is layout mode available in recent browsers. It was created to enable more efficient layout and alignment of elements with dynamic sizes in user interfaces.

### display: flex

To use flexbox to lay out an element's children, set the element's `display` property to `flex`.

```css
.flex-container {
	display: flex;
}
```

[Here's a very basic example of flexbox in use](https://jsbin.com/kagiqu/5/edit?html,css,output). You'll see that by default items inside the flex container stack horizontally and fill the full height of the container.

### flex-grow

In the above example, the widths of the child elements are set explicitly. What if we want them to expand to fill the container instead? The `flex-grow` property allows us to set the way elements expand.

By default, `flex-grow` is assumed to be set to `0`, which means the element will not expand to take up space.

Setting an element's `flex-grow` property to `1` will cause it to try to take up as much space as it can. That looks like this:

```css
.flex-container div {
	flex-grow: 1;
}
```

[Here's a live example](https://jsbin.com/kagiqu/6/edit?html,css,output).

### flex-wrap

By default, a flexbox container will lay out all its children in a single row. If you'd like to create a grid instead, you can use the `flex-wrap` property. Here's the CSS for a container whose children will wrap to the next line:

```css
.flex-container {
	display: flex;
	flex-wrap: wrap;
}
```

[Here's a live example of how that looks](https://jsbin.com/kagiqu/7/edit?html,css,output)

### align-items

The `align-items` property changes how a flexbox container's children are laid out along its major axis (the horizontal axis by default). It looks like this:

```css
.flex-container {
	display: flex;
	align-items: stretch;
}
```

The most commonly used values are:

Value | Effect
----- | ------
`stretch` | Children stretch to fill container (this is the default value)
`center` | Children are centered within the container
`flex-start` | Children stick to the top of the container
`flex-end` | Children stick to the bottom of the container.

[Here are examples of all four values in use](https://jsbin.com/kagiqu/21/edit?html,css,output)

### justify-content

The `justify-content` property controls how a flexbox container's children are distributed along its major axis (again, the horizontal axis by default). It looks like this: 

```css
.flex-container {
	justify-content: space-between;
}
```

The most commonly used values are:

Value | Effect
----- | ------
`center` | Children are grouped together in the center
`flex-start` | Children are grouped together on the left side of the container
`flex-end` | Children are grouped together on the right side of the container
`space-around` | Space around each children is equalized, including space between the first + last children and the container
`space-between` | Space between each child is equalized, but there is no space between the first + last children and the container

The best way to understand these values is to see them in action. [Here are examples of all five of them in use](https://jsbin.com/siqebu/1/edit?html,css,output)

### flex-direction

So far we've talked about using flexbox to lay out horizontal rows and grids, but it can also be used for vertically oriented layouts. The `flex-direction` property controls the orientation of a flexbox container. Here's how it looks in use:

```css
.flex-container {
	flex-direction: column;
}
```

And [Here's an example](https://jsbin.com/lefagay/1/edit?html,css,output) of flexbox being used to create a vertical layout.

## Applications

Flexbox simplifies the creation of a whole bunch of type of layouts. Here some cases where it comes in especially handy.

### Centering an item

Vertically centering dynamically sized content can be done in three lines of code using flexbox.

```css
.flex-container {
	display: flex;
	align-items: center;
	justify-content: center;
}
```
[Here's a live example](https://jsbin.com/lilima/1/edit?html,css,js)

Note that the element stays centered even as its width and height change.

### A simple grid

Creating a grid of items can be done using the `flex-wrap` as shown above.

[Here's a live example](https://jsbin.com/varoqa/3/edit?html,css,output).