# Modules


- reusable pieces of code that can be exported from one program and imported for use in another program
  - find, fix, and debug code more easily
  - reuse and recycle defined logic in different parts of the application
  - keep information private and protected from other modules
  - prevent pollution of the global namespace and potential naming collisions by selecting variables and behavior loaded into a program

- **dependencies:** relationships between modules

![hand drawn x](../img/x-mark.svg)  

## **Exporting Modules:**

---
 In Node.js use: `module.exports`  
   - used for Node.js development 

 In ES6 use: *default export* and *named exports*
   - used for front end development
 
---

## Exporting in Node.js

#### `module.exports` syntax 
 - every JavaScript file run in Node has a local `module` object with and `exports` property
   - defines what should be exported from the file  
---
#### Steps to Export a Module: 
1. Create an object to represent the module  
*Example:*
   ```
    let Colors = {};
   ```
2. Add properties or methods to the module object  
*Example:*
   ```
    Colors.bedroom = "periwinkle";
   ```
3. Export the module with `module.exports`  
*Example:*
   ```
    module.exports = Colors;
   ```
---
- any collection of data and functions can be wrapped in an object and exported with `module.exports`

## Exporting in ES6

### Default Export
- allows export of one module per file 
- used to export JavaScript objects, functions, and primitive data types
- export default replaces module.exports in ES6
- export default not supported by Node.js, 
   - use module.exports in Node.js (back-end development)
   - use export default for front-end development  
*Example:*
   ```
    let Colors = {};

    export default Colors;
   ```

### Named Exports
- allows exporting data using variables
  - each piece of data needs a distinct variable name
  - each export is stored in its own variable-not as a property on an object 
- use the `export` prefix and enclose the objects (string objects and functions) in curly brackets at the end of the file

  *Example:*
   ```
    let wallColor = '';
    function paintBedroom(){
    };
    function paintBathroom() {
    };

    export { wallColor, paintBedroom};
   ```

   - `export { wallColor, paintBedroom}; ` exports objects by their variable names
---
  #### Default Exports and Named Exports can be used together in the same file.  

---

## Export Named Exports
- export the variable as soon as it is declared
- place the `export` keyword in front of the variable declaration 
- export statement at the bottom of the file is no longer needed   `
*Example:*
   ```
   export  let color = '';
   export function paintBedroom() {

      }
   function chooseRug() {
    // note this function is not exported
    }
   ```
## Export as
- changing the name of the variable when exported or imported
- use the `as` keyword


![Arrow right](../img/arrow-right.svg)  

## **Importing Modules:**
---
 In Node.js use: `require()`   
 In ES6 use:  *import* 
 
---

## Importing in Node.js
 - use `require()` function to import modules in Node.js
   - takes a file path argument which points to the original module file
   - `.js` extension is optional and will be assumed if not included
---
#### Steps to Import a Module: 
1. Create a `const` variable
2. Set the new variable equal to the value of the `require()` function
   - note the the file path is a string
   - the `.js` extension is optional

*Example:*
   ```
    const Walls = require('./colors.js');
   ```
3. Use the imported module and its properties in the program  
    - note that the variable associated with the `require()` function is a local variable

*Example:*
```
   function paintBedroom() {
      console.log('Please use ' + Walls.bedroom + ' for this room.');
    }

    paintBedroom();
```
---
## Importing in ES6
- `import` keyword for importing modules
---
#### Steps to Import a Module with ES6 syntax  
*Example:*
   ```
    import Colors from './colors';
   ```
1. Begin statement with the import keyword  

2. Use the name of the variable in which the default export is to be stored
3. `from` signifies location module is loaded from
4. End the statement with the name of the module to be loaded
   - local files can be named without the extension
   - file path must be a string
---

### Named Imports

- use the `import` keyword to import objects stored in a variable
  - include the variables in a set of brackets `{}`
- omit any unwanted variables from the `import` statement

  *Example:*
   ```
    import { walls, paintBedroom} from './colors';
   ```
### Import Named Imports
- use the original syntax describing the variable name

*Example:*
   ```
    import { walls, paintBedroom,} from 'colors';
   ```

### Importing aliases
- add the aliased variable to the import statement
- may alias an object not previously aliased when exported
- also: may import an entire module as an alias
---
#### A collection of objects and functions can be imported with the same data.

---


