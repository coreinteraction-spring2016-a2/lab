# Class assignment

Folder name: `week-8-class-assignment`

# Practice problems

1. Write a function called `getFirst` that returns the first element in an array.

`[4, 13, 87]` -> `4`

```javascript
var testArray = [4, 13, 87];
var result = getFirst(testArray);
console.log(result); // Should print 4
```

2. Write a function called `getLast` that returns the last element in an array.

`[4, 13, 87]` -> `87`

```javascript
var testArray = [4, 13, 87];
var result = getLast(testArray);
console.log(result); // Should print 87
```

3. Write a function called `findLargest` finds the largest number in an array.

`[4, 13, 87]` -> `87`

```javascript
var testArray = [4, 13, 87];
var result = findLargest(testArray);
console.log(result); // Should print 87
```

4. Write a function called `decrementArray` that subtracts 1 from each number in an array.

`[4, 13, 87]` -> `[3, 12, 86]`

```javascript
var testArray = [4, 13, 87];
decrementArray(testArray);
console.log(result) // Should print [3, 12, 86]
```

5. Write a function called `addHello` that adds the string `'hello '` to each item in an array.

`['sweet', 'sphere', 'stream']` -> `['hello sweet', 'hello sphere', 'hello stream']`

```javascript
var testArray = ['sweet', 'sphere', 'stream'];
addHello(testArray);
console.log(testArray); // Should print ['hello sweet', 'hello sphere', 'hello stream']
```

6. Write a function called `appendSomething` that adds the string `something` as the last element in an array. 

`[4, 13, 87]` -> `[4, 13, 87, 'something']`

```javascript
var testArray = [4, 13, 87];
appendSomething(testArray);
console.log(testArray) // Should log [4, 13, 87, 'something']
```

7. Write a function called `listProps` that prints the name of each property in an object.

`{ a: 1, b: 2 }` -> print `'a'` then `'b'`