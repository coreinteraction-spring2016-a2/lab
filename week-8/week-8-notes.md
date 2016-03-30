# Arrays and objects

## Arrays

### Creating an array

Arrays can be used to store lists of variables. You can create an array like this:

```javascript
var myArray = [
	'hello',
	'goodbye',
	'what??'
];
```

Arrays can be used to store any type of data, including functions.

```javascript
var myArray = [
	true,
	'what?',
	0,
	function () {}
];
```

Arrays can be used to store other arrays.

```javascript
var myArray = [
	[0, 1],
	[5, 7],
	[12, 15]
];
```

### Accessing items in an array

An item's position in an array is called its **index**. The index of the first item in an array is `0`. Take a look at this array:

```javascript
var testArray = [
	'abc',
	'def',
	'ghi'
];
```

In the above array, the index of `'abc'` is `0`, the index of `'def'` is `1`, and the index of `'ghi'` is `2`.

You can use an item's index to retrieve it from an array. Here's an example:

```javascript
var otherArray = [
	'dog',
	'gecko',
	'swan'
];

var a = otherArray[0];
var b = otherArray[1];
var c = otherArray[2];

console.log(a); // Will print 'dog'
console.log(b); // Will print 'gecko'
console.log(c); // Will print 'swan'
```

You can also set the value of an array at an index.

```javascript
var heavyArray = [
	'yellow',
	'green',
	'brown'
];

heavyArray[1] = 'purple';

console.log(heavyArray); // Will print ['yellow', 'purple', 'brown']
```

### Adding items to an array

The most common way of adding items to an array is using the `push` function. `push` adds an item to the end of an array. It's used like this:

```javascript
var coolArray = [];

coolArray.push('hello');
console.log(coolArray); // Will print ['hello']

coolArray.push('goodbye');
console.log(coolArray); // Will print ['hello', 'goodbye']
```

You can also add items to an array using indexes. 

```javascript
var greenArray = [];

greenArray[0] = 'wazzap';
greenArray[1] = 'test test';

console.log(greenArray); // Will print ['wazzap', 'test test']
```

### Getting the length of an array

```javascript
var funNumbers = [42, 57, 111];

console.log(funNumbers.length); // Will print 3
```

Knowing the length of an array allows you to get the last value in that array. Since array indexes start at `0`, the index of the last item will be 1 less the the array's length.

```javascript
var numbers = [1, 2, 3];
var last = numbers[numbers.length - 1];
console.log(last); // Will print 3
```

### Iterating over an array

Often you'll want to perform some action for each item in an array. The most common way of doing that is using a `for` loop.

```javascript
var wordArray = [
	'ham',
	'globe',
	'quartz'
];

for (var i = 0; i < wordArray.length; ++i) {
	wordArray[i] = 'hello ' + wordArray[i];
}

console.log(wordArray); // Will print ['hello ham', 'hello globe', 'hello quartz']
```

## Objects

### Creating an object

Objects can be used to group named values. You create an object like this

```javascript
var imageData = {
	photo: 'red.jpg',
	width: 300,
	height: 200,
	caption: 'This is something red'
};
```

### Accessing object properties

There are two ways to access a property of an object. Here's what you'd do when you know the name of the property you want to access:

```javascript
var size = {
	width: 200,
	height: 300
};

var width = size.width;
console.log(width); // will print `200`
```

And here's what you'd do when you don't know the name of the property you're accessing:

```javascript
var size = {
	width: 200,
	height: 300
};

var propertyToAccess = 'width';

var value = size[propertyToAccess];
console.log(value); // will print 200
```

### Iterating over object properties

There are times when you may want to perform an action for each of an objects properties. You can use a for-in loop to do so:

```javascript

var size = {
	width: 200,
	height 300
};

for (var key in size) {
	console.log(key, size[key]); // will print 'width 200' then 'height 300';
}
```