## **Iterators**
---
### **Higher Order Functions**
- functions that accept other functions as arguments and/or return functions as output
- used to build abstractions on other abstractions
- helps with writing modular code which is easier to read and debug
- callback functions can be:
  - pre-defined
  - function expression
  - arrow function

### **Functions as Data**
- functions can be reassigned to a new variable that holds a reference to the original function
- reassign the function without using parentheses (assign the value of the function itself, not the value it returns when invoked)
- the new function name can be invoked with parentheses in the same way as the original function

### **Properties of Functions**
- use the dot operator `.` to access a function’s name property (similar to other objects' properties)

- *Examples:* 
  - `.length`
  - `.name`
  - `.toString()`


### **Functions as Parameters**
- **Callback Functions:** functions that are passed in as parameters and invoked in the execution of the higher-order function
  - pass in the function without the parentheses (including parentheses would call the result of the function, not the function)

### **Iterators (Iteration Methods)**
#### Iteration Methods
- also called **iterators**
-  methods called on arrays to manipulate elements and return values  
- Complete List of built-in array methods:  
  - [MDN’s Array iteration methods page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Iteration_methods)

### `.forEach()`

  - calls a function for each element in an array (same output as using the `for` loop)  
  - executes the same code on every element in an array but does not change the array
  - returns `undefined`

*Example using a function expression:*
```
const trees = ['palm', 'spruce', 'elm', 'willow'];

trees.forEach(function(shade) {
    console.log(`This ${shade} will keep us cool.`);
  });

// returns:
This palm will keep us cool.
This spruce will keep us cool.
This elm will keep us cool.
This willow will keep us cool.
```
*Example using an arrow function (ES6):* 
```
const trees = ['palm', 'spruce', 'elm', 'willow'];

trees.forEach(shade => console.log(`This ${shade} will keep us cool.`));

// returns:
This palm will keep us cool.
This spruce will keep us cool.
This elm will keep us cool.
This willow will keep us cool.
```
- may also define a function beforehand to use as the callback function in the `.forEach` function

### `.map()`
- executes the same code on every element in an array and returns a new array with the updated elements 
- the `map()` method must be assigned to a new variable
- similar to `.forEach`, except that it returns a new array

*Example using an arrow function:*
```
const prices = [7, 5, 18, 27.4];

const discount = prices.map(price => {
  return price * 0.85;
});
console.log(discount);

// returns:
[ 5.95, 4.25, 15.299999999999999, 23.29 ]
```


### `.filter()`

- creates a new array with the elements that pass the result of a given test
- returns a new array
- the `filter()` method must be assigned to a new variable 
- does not mutate the original array
- the callback function should return `true` or `false` for each element passed into it
- elements that evaluate to `true` are added to the new array

*Example using a function expression:*
```
const prices = [7, 5, 18, 27.4];

const cheapItems = prices.filter(function(price) {
  return price < 10;
});

console.log(cheapItems);

// returns:
[ 7, 5 ]
```

*Example using an arrow function:*
```
const prices = [7, 5, 18, 27.4];

const cheapItems = prices.filter(price => {
  return price < 10;
});
console.log(cheapItems);

// returns:
[ 7, 5 ]
```

### `.findIndex()`

- returns the index of the first element in an array that passes a given test
- must evaluate to `true` in the callback function
- useful when working with arrays containing many items  
- if no element in the array evaluates to `true` returns `-1`

*Example using an arrow function:*
```
const prices = [7, 5, 18, 27.4];

const cheapestItem = prices.findIndex(price => {
  return price < 7;
});
console.log(prices[cheapestItem]);

// returns:
5
```

### `.reduce()`

- iterates through an array and takes the values of the elements and returns a single value.
- commonly used with numbers, such as finding the sum of all the numbers in an array
- does not mutate the original array
- callback function has two parameters:
  - **accumulator:** begins as the value of the first element in the array, then continues as the return value of the callback function
  - **currentValue:** begins as the second element in the array, then takes the value of the current element in the looping process  
  - can take an optional second parameter to set a value for the accumulator other than the first array element 
- an optional second parameter can be added as the initial accumulator value  

*Example using an arrow function:*
```
const prices = [7, 5, 18, 27.4];

const totalPurchase = prices.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
});

console.log(totalPurchase);

// returns:
57.4
```

*Example using an arrow function with second argument:*
```
const prices = [7, 5, 18, 27.4];

const totalPurchase = prices.reduce((accumulator, currentValue) => {
  return accumulator + currentValue
}, 15);

console.log(totalPurchase);

// returns:
72.4
```

### `.every()`


   - `.some()`
   - `.find()` 
     - returns the first value in an array that passes a given test
     - can help with arrays that contain many values
   - `.includes()`
     - iterates through array and evaluates `true` if array element passes test


