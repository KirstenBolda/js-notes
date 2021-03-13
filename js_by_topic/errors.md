# Errors

- JavaScript errors are objects that have a name and message property  
  - built-in errors alert programmers about common mistakes in the code
  - use the `Error` function to make an error object with a message unique to the program
  - errors will prevent a program from executing unless they are handled


**Error Handling:** process of programmatically anticipating and addressing errors

### Error Handling Keywords:  
`try` ... `catch`
- used to anticipate and handle errors
1. Evaluate the code in the `try` block
2. Handle the error in the `catch` block
- code following the `try` keyword is enclosed in curly braces `{}`
   - called the *try block*
   - insert the code that may throw an error in the try block
- the catch statement accepts the error thrown in the try block and is enclosed in curly braces `{}`
  - called the *catch block*

Syntax for a `try ... catch` statement:
```
try {
  // try block code
} catch (e) {
  // catch block code
}
```
- can also use `try ... catch` to handle built-in errors thrown by the JavaScript engine
  - useful for using data from an external source not written directly in the program
  - allows the program to continue running and print a message to indicate what went wrong

`throw`
- creating the error does not stop the program from running, the error must be thrown for it to halt the program
- use the `throw` keyword to throw the error
- code after the `throw` statement will not execute
- after the `throw Error('statement goes here');` line is executed, the error object is thrown and the code after it will not run

## Error Stack Traces
- printed message containing information about where the error occurred, what type of error was thrown, and a description of the error
- appear when the compiler (which translates code for the computer to understand and run) can't interpret the code
- compiler throws an error showing that it stopped and why 

*Examples:*

`/documents/importantFile.js:10`    (Error location: path and line)

`ReferenceError: `   (Type of error)

`colorVariable is not defined`   (Error message)

## Built-in runtime errors
Examples:
`ReferenceError`: occurs when a variable or function cannot be found
`TypeError`: occurs when a value is not a valid type

## Three questions to ask when debugging an error:

1. On what line did the error occur?  
2. What type of error was thrown?  
3. What is the error message?  

## JavaScript Error Types

Three Common Error Types:  
1. `SyntaxError`
- thrown when a typo causes invalid code
  - improperly open or closed brackets, parentheses
  - invalid semicolons or commas
2. `ReferenceError`
- thrown by referencing a variable that doesn't exist
  - make sure all variables are properly declared
3. `TypeError`
- thrown when attempting to perform an operation on a value of the wrong type

Four Other Error Types:  
- `EvalError`
- `InternalError`
- `RangeError`
- `URIError`

## Debugging Errors

1. Run the code. Identify the first error's stack trace, type, description and location.
2. Go to the location indicated by the stack trace and identify the bug using the error type and description
3. Fix the bug and re-run the code.
4. Repeat steps 1 through 3 until the code no longer throws errors

## Finding Silent Bugs

- lack of thrown errors doesn't necessarily mean the code logic is correct
- code may return incorrect values without throwing errors
- `console.log` is a powerful tool for locating silent bugs

## Debugging with `console.log()`

Steps to debug with `console.log()`
1. Print out all starting variables, existing values and arguments using `console.log()`. If all is well go to step 2  
2. At the next piece of logic use `console.log()` to make sure variables have the expected values and that the code is being executed. Repeat until a line that isn't working is revealed.
3. Fix the bug and run the code again. If further problems persist, return to step 1.

## Using the Error function to create custom error messages
- error function takes the argument of a string that becomes the value of the error's `message` property
- a created error will not cause the program to stop running
  - a thrown error will stop the program from running

*Example:*
```
console.log(Error('Please enter your first name.'));
// Prints: Error: Please enter your first name.
```

