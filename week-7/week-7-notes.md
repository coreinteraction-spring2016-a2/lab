# Javascript

## Variables

You can use variables to store information. Here's how that looks:

```javascript
var a = 1;

console.log(a); // Will print `1`

var b = a;

console.log(b); // Will print `1`
```

You need to use the `var` keyword when defining a variable's initial value, but not to set its value after that.

```javascript
var a = 1;
console.log(a) // Will print `1`

a = 2;
console.log(a) // Will print `2`
```

Variables can store a number of different types of data. The simplest are numbers, text (called strings), and true/false values (called booleans).


### Numbers

Numbers look like numbers. You can do math with them.

```javascript
var a = 1;

var b = a + 1;
console.log(b); // Will print `2`

var c = a - 1;
console.log(c); // Will print `0`

var d = a * 2;
console.log(d); // Will print `2`

var e = a / 2;
console.log(e); // Will print `.5`
```

You can increment or decrement a number in place using the `++` and `--` operators.

```javascript
var a = 1;
++a;

console.log(a); // Will print 2

var b = 1;
--b;
console.log(b); // Will print 0
```

You can use the built in `Math` object to do fancier math, like so:

```javascript
var a = 2;

var b = Math.pow(a, 2);
console.log(b); // Will print 4;
```

[Read more about fancy math methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

### Strings

Strings store text values. A string looks like some text with quotes around it. You can use either double or single quotes when defining a string, but not curly or other special quotes.

```javascript
var a = 'hello';
var b = "goodbye";

console.log(a); // Will print `hello`
console.log(b); // Will print `goodbye`
```

You can combine strings using the `+` operator.

```javascript
var a = 'hello';
var b = 'goodbye';

var c = a + b;
console.log(c); // Will print `hellogoodbye`;

var d = a + ' ' + b;
console.log('hello goodbye'); // Will print `hello goodbye`
```

### Booleans

There are two boolean values, `true` and `false`

```javascript
var a = true;
var b = false;

console.log(a); // Will print `true`
console.log(b); // Will print `false`
```

## Conditional logic

Sometimes you'll want your program to change the function it performs in different circumstances. Conditional logic (using `if` and `else` statements) is a way of making that happen.

### `if` statements

If statements execute code when certain conditions are true. Here's an example:

```javascript
var a = true;

// Will print 'true'
if (a) {
	console.log('true');
}
```

They can be combined with `else` statements. As their name implies, `else` statements are executed if their corresponding `if` statement is not true.

```javascript
var a = false;
var b = true;

// Will print 'no'
if (a) {
	console.log('yes');
} else if (b) {
	console.log('no');
} else {
	console.log('idk');
}
```

### Comparing variables

It's often useful to compare variables in conditionals. The most common comparison you'll make is checking whether a variable is equal to a particular value. Here's how you do that:

```javascript 
var appleCount = 5;

if (a == 5) {
	console.log('you have 5 apples!');
} else {
	console.log('you have some other number of apples');
}
```

You can test whether a number is _not_ equal to another number using `!=`.

```javascript
var appleCount = 3;

if (appleCount != 0) {
	console.log('you have some apples!');
} else {
	console.log('you have no apples');
}
```

You can compare the relative sizes of numbers using `<` (less than) and `>` (greater than).

```javascript
var appleCount = 3;

if (appleCount > 0) {
	console.log('there is at least one apple');
} else if (appleCount < 10) {
	console.log('there are fewer than 10 apples');
} else  if (appleCount > 20) {
	console.log('there are really a lot of apples!');
}
```

## Loops

You'll often want to repeat the same action a number of times. You can do this using loops. The most common loop is the `for` loop. 

```javascript
for (var i = 0; i < 10; ++i) {
	console.log('This loop has run ' + i + ' times');
}
```

Another type of loop you'll sometimes see is the `while` loop. A while loop will continue executing until its condition is no longer true.

```javascript
var x = 0;
while (x < 10) {
	console.log('still running');
	++x;
}
```

One downside to `while` loops is that it's easy to create a condition that will always be true. Doing so will cause the loop to run over and over until your page crashes.

```javascript
// This will crash your webpage!!!!!
while (true) {
	console.log('hi!');
}
```
## Functions

Functions are reusable pieces of code. Here's a very simple function:

```javascript
var add = function (first, second) {
	return first + second;
}

var result = add(1, 2);
console.log(result); // Will print `3`
``` 

There's also a shorthand form for defining functions. This will return the same result as the function above:

```javascript
function add (first, second) {
	return first + second;
}
```