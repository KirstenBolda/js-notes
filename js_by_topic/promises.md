# Promises

### Promise: objects that represent the eventual outcome of an asynchronous operation
- Three states:
    1. Pending: initial state, operation has not completed yet
    2. Fulfilled: operation has successfully completed, the promise has a resolved value
    3. Rejected: operation has failed, the promise has a reason for failure--usually an `Error`

- Settled: promise no longer pending, it is either fulfilled or rejected

## Constructing a Promise Object

#### Syntax: use the `new` keyword and the `Promise` constructor method
 - Promise constructor method takes an executor function parameter
 - Executor function:
   - runs automatically when the constructor is called
   - starts an asynchronous operation
   - dictates how the promise should be settled
 - Executor function takes two parameters: (not defined by the programmer)
   - `resolve()`
     - has one argument
     - will change the promise's status from `pending` to `fulfilled`
     - resolved value will be set to argument passed in
   - `reject()`
     - takes a reason or error as an argument
     - will change the promise's status from `pending` to `rejected`
     - rejection reason will be set to the argument passed in

## Node `setTimeout()` function

- used in functions that return promises which settle after some time
    - uses callback functions to schedule tasks to be performed after a delay
    - has two parameters:
      - callback function
      - delay in milliseconds
    - delay is performed asynchronously: the rest of the program doesn't stop executing during the delay

Event-loop: after the specified time the callback function is added to the line of code waiting to be run
  - synchronous code in the program will run first
  - then any code in front of it in the line will run
  - then the callback function will run, therefore the delay may be longer than the specified delay


## Consuming Promises

### States of an asynchronous promise:
 - pending - initial state
 - settled - complete
 - `.then()` - next step after promise settles
   - higher-order function
   - takes two callback functions as arguments
     - the two callback functions are called handlers
     - First handler (`onFulfilled`) : success handler
       - contains logic that follows the promise resolving
     - Second handler (`onRejected`) : failure handler
       - contains logic in the case of the promise rejecting
   - can be invoked with one, both or neither handler
   - `.then()` always returns a promise

### Handling a successful, resolved, promise:
- invoke `.then()` on the promise and pass in the sucess handler callback function

## Using catch() with Promises

- use the principle of separation of concerns 
- separate resolved logic from rejected logic
- chain a first `.then()` with the success logic to a second `.then()` with the failure logic





