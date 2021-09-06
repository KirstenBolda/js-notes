## **Methods**

---

- actions that can be performed in JavaScript.

- when data stored on an object is a function- a method is what an object does

- Properties that hold function values are called **methods** of the value they belong to.
- Methods are called by appending a JavaScript instance (an object) with a period (dot operator) followed by the name of the method and opening and closing parentheses.

  - _Example:_ `'example string'.methodName();`

- A familiar example: `console.log()` -calling the `.log() `method on the `console` object.

---

## Built-in String Methods

**Calling a built-in string method:**

- append a string instance with:
  - the dot operator
  - the method name
  - opening and closing parentheses
- string methods return strings so they can be chained

## _Examples:_

### **`.toUpperCase()`**

- capitalize all letters in the value entered

_Example:_

```
const myCat = 'Newton';

console.log(myCat.toUpperCase());
//returns NEWTON

const favoriteFood = 'Tuna Kibble with Gravy'
const favoriteFoodCaps = favoriteFood.toUpperCase()
console.log(favoriteFoodCaps);
// returns TUNA KIBBLE WITH GRAVY

```

_Example:_

- how to capitalize the first letter of an array of words:

```
const myCats = ['newton', 'galileo','rutherford']

```

- split the parts of each name into an array and capitalize the first letter of each array element

```
const capitalizeCats = function(catNames) {
  const namesUpper = [];
  for (const name of catNames) {
    namesUpper.push(name.replace(name[0], name[0].toUpperCase()))
  }
  return namesUpper;
}
capitalizeCats(myCats);
// returns ["Newton", "Galileo", "Rutherford"]
```

_Example:_

- how to capitalize the first letter of each part of a name

```
const capName = function (fullName) {
  // split the full name into an array of individual names
  const nameArray  = fullName.split(" ");
  console.log(nameArray)
  // create an empty array for the capitalized names
  const nameCapitalized = []
  // use .replace() to capitalize the first letter of each name and push each name into the nameArray
  for (const name of nameArray) {
    nameCapitalized.push(name.replace(name[0],name[0].toUpperCase()))
  }
  // return the nameCapitalized array and join the names into a string
  return nameCapitalized.join(' ')
}
```

- test the capitalize function

```
const inventor = 'alan mathison turing';
capName(inventor);
// returns "Alan Mathison Turing"
```

### **`.toLowerCase()`**

- convert all letters in the valued entered to lower case

_Example:_

```
const catFood = 'Kibbles';
console.log(catFood.toLowerCase());
// returns kibbles (string)
```

### **`.trim`**

- removes white space from both beginning and end of string
- after ES2019 .trimStart() and .trimEnd() can trim from beginning or the end of a string

_Example:_

```
const catPerch = '  couch   '
console.log(catPerch.trim())
// returns couch
```

_Example with chaining:_

- note that string methods can be used directly on the string

```
console.log(' CatNip  '.toLowerCase().trim())
// returns catnip
```

### **`.slice`**

- cuts the string off at the first parameter and returns a substring with characters remaining after the slice, beginning with the character at the input location

_Example:_

```
const catType = 'Abyssinian'
console.log(catType.slice(5))
// returns: inian
```

- inputting two parameters, start and end, returns a substring including the first parameter, but not the end parameter character

```
const catType = 'Maine Coon'
console.log(catType.slice(0, 5))
// returns: Maine
```

### **`.split`**

- break the string into an array separated by the character input

_Example:_

```
const catToys = 'pompom+catnip+feather';
console.log(catToys.split('+'));
// returns ["pompom", "catnip", "feather"]
```

### **`.join`**

- joins all the elements of an array into a string with the character input between them
- opposite of `.split()` method

_Example:_

```
const catTreats = ["kibbles", "catnip", "tuna"];
console.log(catTreats.join('+'));
// returns kibbles+catnip+tuna
```

### **`.replace`**

- replace a part of a string with another substring
- creates a new string, doesn't mutate the original string

_Example:_

```
const favoriteActivities = 'Jumping and hiding and chasing.';
console.log(favoriteActivities.replace('chasing','sleeping'));
// returns Jumping and hiding and sleeping.
```

### **`.replaceAll()`**

- replaces all occurences of a string with the second parameter string

_Example:_

```
const todaysSchedule = 'Each cat should have 15 chicken kibbles and one can of beef slices. Then, before bed, 5 more chicken kibbles.';
console.log(todaysSchedule.replaceAll('chicken','tuna'));
// returns: Each cat should have 15 tuna kibbles and one can of beef slices. Then, before bed, 5 more tuna kibbles.
```

### **`.padStart()`**

- pad the string to the desired length by adding characters to the beginning
- two arguments: first desired length of the string, second the character for padding

_Example:_

```
const catTalk = 'Meow';
console.log(catTalk.padStart('10', '*'))
// returns '******Meow'
```

### **`.padEnd()`**

- pad the string to the desired length by adding characters to the end
- two arguments: first desired length of the string, second the character for padding

_Example:_

```
const catTalk2 = 'Meow';
console.log(catTalk2.padEnd('12', '*'))
// returns 'Meow********'
```

### **`.repeat()`**

- repeats the string the number of times in the parameter

_Example:_

```
const hungryCat = 'Meow ';
console.log(hungryCat.repeat(6));
// returns 'Meow Meow Meow Meow Meow Meow '
```

### **`.indexOf()`**

- returns the position of the first occurrence of the letter or string in the parameter

_Example:_

```
const randomString = 'nDii!JZ-L-EFuraQHdT!xYr_UchUmb';
console.log(randomString.indexOf('!'))
// returns 4
```

## Boolean String Methods

### **`.includes()`**

- returns true if a string combination is somewhere in the string

_Example:_

```
const favoriteFoods = 'chicken, tuna, beef, cheese.';
console.log(favoriteFoods.includes('tuna'));
// returns true
console.log(favoriteFoods.includes('turkey'));
// returns false
```

_Example:_

- search a long string

```
console.log('bMD3tM7Hxyvqw4vLs9igkUrZryTD8ep9s8rL'.includes('1'));
// returns false
console.log('bMD3tM7Hxyvqw4vLs9igkUrZryTD8ep9s8rL'.includes(9));
// returns true for both '9' and 9
console.log('bMD3tM7Hxyvqw4vLs9igkUrZryTD8ep9s8rL'.includes('TD'));
// returns true
```

### **`.startsWith()`**

- returns true if the string combination is at the beginning of the string

_Example:_

```
const favoriteFoods = 'chicken, tuna, beef, cheese.';
console.log(favoriteFoods.startsWith('chick'));
// returns true
console.log(favoriteFoods.startsWith('cheese'));
// returns false
```

### **`.endsWith()`**

- returns true if the string combination is at the end of the string
  _Example:_

```
const favoriteFoods = 'chicken, tuna, beef, cheese.';
console.log(favoriteFoods.endsWith('chick'));
// returns false
console.log(favoriteFoods.endsWith('cheese'));
// returns true
```

---

[Complete list of built in string methods at MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

---

## Built-in Math Methods

**Calling a built-in Math method:**

- append the Math method with:
  - the dot operator
  - the method name
  - opening and closing parentheses

### **`Math.random()`**

- generates a decimal between 0 and 1

- to generate a random number in a range, multipy by the highest number in the range

_Example:_
`Math.random() * 100;`: generates a number between 1 and 100:

### **`Math.floor()`**

- rounds a decimal number down to the nearest whole number
  _Example:_

```
Math.floor(76.129); // returns 76
```

### **`Math.ceil()`**

- rounds a decimal number down to the nearest whole number
  _Example:_

```
Math.ceil(76.129); // returns 77
```

Combine methods: Round down `Math.random()` to nearest whole number

_Example:_
Generate a random whole number between one and one hundred:

```
Math.floor(Math.random() \* 100); // returns an integer between one and one hundred
```

### **`Math.max()` and `Math.min()`**

- returns the largest or smallest of the numbers passed in as parameters
  _Examples:_

```
Math.max(4, 7.5, 18, 63.2, 2.8, 3.45); // returns 63.2

Math.min(4, 7.5, 18, 63.2, 2.8, 3.45); // returns 2.8
```

### **`Math.pow()`**

- returns the base number to an exponent
- takes two parameters

  _Example:_

```
Math.pow(2, 10); // returns 1024
```

[MDN: Built-in Math Object methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

[MDN: Built-in Number Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
.
.

## Creating Methods

- may be defined using anonymous arrow function expressions

  **Anonymous Arrow Function**

  - `sputter: () => { console.log('The engine sputters...');`

- may be defined with shorthand method syntax

  **Shorthand Method Syntax**

```

     start(adverb) {
       console.log(`The engine starts up ${adverb}...`);
     },
      },

```

#### Getters

- Methods that get and return internal properties of an object
- use the `get` keyword followed by the function
- don't need to be called with parentheses, syntax appears the same as accessing a property
- getter method cannot have the same name as a property

#### Setters

- Reassign values of existing properties within an object
- don't need to be called with parentheses, syntax appears the same as resassigning the value of a property
- All setters need at least one parameter to provide a parameter

#### Factory Functions

- function that returns an object and can be reused to make multiple object instances
- can have parameters allowing us to customize the object that gets returned

#### Built-in Methods for Arrays

- **Mutator** methods: modify the original array
- **Accessor** methods: methods that return a new value or representation
- **Iteration** methods: methods that operate on every item in an array, one at a time.

![curly line](../img/curly-narrow.svg)![curly line](../img/curly-narrow.svg)![curly line](../img/curly-narrow.svg)![curly line](../img/curly-narrow.svg)![curly line](../img/curly-narrow.svg)![curly line](../img/curly-narrow.svg)![curly line](../img/curly-narrow.svg)

#### Iteration Methods

- also called **iterators**
- methods called on arrays to manipulate elements and return values
- [MDN’s Array iteration methods page.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Iteration_methods)
  _Examples:_

- `.forEach()`
  - calls a function for each element in an array (same output as using the `for` loop)
  - does not change the array and returns `undefined`
- `.map()`
  - creates a new array with the results of a function call on each element in the array,
  - the `map()` method must be assigned to a new variable
- `.filter()`
  - creates a new array with the elements that pass the result of a given test,
  - the `filter()` method must be assigned to a new variable
  - does not mutate the original array
    _Example:_

```

// the original array
const firstNames = ['Teisha', 'Taylor', 'Pearl', 'Reese', 'Lynne', 'Tegan'];
// the filter function
const namesLetterT = firstNames.filter( name => {
return name[0] === 'T';
})
// the newly created array
console.log(namesLetterT); // logs [ 'Teisha', 'Taylor', 'Tegan' ]

```

- `.findIndex()`
- returns the first index in an array that passes a given test
- useful when working with arrays containing many items
  returns `-1` if none of the elements in the array satisfies the condition
- `.reduce()` -

- will reduce an array to a single value
- seen commonly with numbers, such as finding the sum of all the numbers in an array
- does not mutate the original array
- the `accumulator` is the first value in the array of numbers, the `currentValue` is the second number in the array
- can also take an optional second parameter to set an initial value for `accumulator` (remember, the first argument is the callback function!)

_Example:_

```

const newNumbers = [1, 3, 5, 7];

const newSum = newNumbers.reduce((accumulator, currentValue) => {
console.log('The value of the accumulator: ', accumulator);
console.log('The value of the currentValue: ', currentValue);
return accumulator + currentValue;
}, 10)
/_ logs:
The value of the accumulator: 10
The value of the currentValue: 1
The value of the accumulator: 11
The value of the currentValue: 3
The value of the accumulator: 14
The value of the currentValue: 5
The value of the accumulator: 19
The value of the currentValue: 7
_/
console.log(newSum); // logs 26

```

- `.every()`
- `.some()`
- `.find()`
- returns the first value in an array that passes a given test
- can help with arrays that contain many values
- `.includes()`
- iterates through array and evaluates `true` if array element passes test
- `.split()`
- splits a string at a designated parameter, often a space

---

#### Returning a letter in a string

- `return string[i]` where `i` is the index position of the letter you want to return
- `.charAt(i)` where `i` is the index position of the letter you want to return

---

```

```

```

```
