# Introduction to Classes

#### Object-Oriented Programming (OOP) Language
 - can be used to model real-world items
 -  set of techniques that use objects (and related concepts) as the central principle of program organization
 - dividing programs into smaller pieces and make each piece responsible for managing its own state
 #### Examples of OOP Languages:
 - JavaScript
 - Python
 - Ruby

 #### Encapsulation: separating interface from implementation
 - public: properties that are part of the interface
 - private: properties not accessible by outside code

## Classes:
 - syntax for creating objects
 - JavaScript class is a type of function
   - declared with the `class` keyword
 - specify the properties and methods of objects they produce
 - used to quickly produce similar objects by serving as a template to create new objects
 - reduce duplicate code and debugging time

## Constructor Method
- called every time JavaScript instantiates a class
- accepts arguments
- used to set initial values for the object
- use the `this` keyword to refer to an instance of the class

#### Constructor Method Syntax
- create a class with a name 
  - capitalize and use CamelCase
- enclose the class between curly brackets `{}`
- create a `constructor()` method with parameters
- enclose the `constructor()` method between curly brackets `{}`
- create properties corresponding to the parameters listed in the constructor method using the `this` keyword

### Class Instance:
- an object that contains the property names and methods of the class
- has unique property values
- use the `new` keyword to create an instance of a class
- prepend property names with underscores to indicate they should not be accessed directly
*Example:*
 - `this._name = name;`
 - `this._color = color;`

#### Class Instance Syntax
- create a new variable to store an instance of the class
- use the `new` keyword to generate an instance of the class
  - the new keyword will call the `constructor()`, run the code inside it and return the new instance
- pass the parameter to the argument to assign it to the associated property

*Example: class with a constructor method*  
```
class Pet {
  // constructor method used to set initial values for the object
  constructor() {
   this.species;
   this.habitat; 
  }
  // method for this class 
  feed() {
console.log('Pet is hungry!');
  } 
}
```

*Example: Create a new instance of the class*
```
const myPet = new Pet();
myPet.feed();
// result would be 'Pet is hungry!'
```
---
### Don't include commas between methods in classes!
 - getter methods and other methods are all listed without any punctuation between them

---

### Method Calls
- used to access and manipulate data in a class instance
- same syntax for method and getter calls on an instance of a class as for objects
  - append the instance name with a dot
  - add the property or method name
  - include opening and closing parentheses for methods

## Inheritance
- used when multiple classes share properties and methods
- decreases amount of code
- create a parent class (superclass)
  - has properties and methods shared by multiple child classes (subclasses)
- child (subclasses) inherit properties and methods from their parent classes
- extend shared properties from parent class to child class
  - use the `extends` keyword
  - makes the methods of the parent class available to the child class
- `super`  calls the constructor of the parent class
  - always call the `super` before using the `this` keyword
- methods and getters are inherited from the parent class just like properties and methods
- child classes can contain their own properties, getters, setters, and methods in addition to those of their parent classes

## Static Methods
- are called on the class itself, not on its instances
- tend to be general utility methods  
*Example:*  
`Date.now()`




