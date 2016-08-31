# FCC-Sum-all-numbers-in-a-range
## Find the sum of an array's largest and smallest values, and everything in between them

We'll pass you an array of two numbers. Return the sum of those two numbers and all numbers between them.

The lowest number will not always come first.

```javascript
function sumAll(arr) {
  return 1;
}

sumAll([1, 4]);
```
---

To start, we should find out what our lowest and highest numbers in the array are, regardless of what index they may be at. We can do this using
the Math.max and Math.min functions. We will also need an empty array for later.

```javascript
function sumAll(arr) {
  var newArr = []; // empty array
  var top = Math.max.apply(null, arr); // returns max value of arr
  var bottom = Math.min.apply(null, arr); // returns min value of arr
  
  return 1;
}

sumAll([1, 4]);
```
---

Next, we're going to push the values of bottom through top and every number between them into our newArr variable with a for loop.

```javascript
function sumAll(arr) {
  var newArr = []; 
  var top = Math.max.apply(null, arr); 
  var bottom = Math.min.apply(null, arr);
  
  for (var i = bottom; i <= top; i++) {
    newArr.push(i); // Returns newArr = [1,2,3,4]
  }
  
  return 1;
}

sumAll([1, 4]);
```
---

To finish off we make another variable to store our sum, using the reduce method with a callback function that adds together all the values
in an array, we can return the total for our final answer.

```javascript
function sumAll(arr) {
  var newArr = [];
  var top = Math.max.apply(null, arr);
  var bottom = Math.min.apply(null, arr);
  
  for (var i = bottom; i <= top; i++) {
    newArr.push(i);
  }
  
  var total = newArr.reduce(function (a,b) {
    return a+b; // Adds 1 + 2 / 3 + 3 / 6 + 4
  }, 0);
  
  return total; // Returns 10
}

sumAll([1, 4,]);
```
