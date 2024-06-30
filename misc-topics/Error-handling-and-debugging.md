# Error Handling And Debugging 

### Q1: What is Error Handling ? In how many ways you can do error handling in Node.js 

**Answer**:Error handling is the process of managing errors that occur during the execution of a program or system 

There are 4 ways to implement error handling in Node.js

1. try-catch(Sync)
2. Error-First Callbacks(Async)
3. Promises(Async)
4. try-catch with async-await(Async)

### Q2: How to handle errors in synchronous operations using try-catch-finally ? 

**Answer**:

 try - a try block is a block of code inside which any error can occur catch- when any error occur in try block it is passed to catch block to handle it 

finally - The finally block is used to execute a given set of statements , whether an exception occur or not 

```javascript
try {

  throw new Error("Synchronous error");

} catch (error) {

  console.error("Error caught:", error.message);

} finally {

  console.log("Finally block executed");

}

//Output :

// Error caught : Synchronous error

//Finally block executed 
```

### Q3: What us Error-First Callbacks ? 

**Answer**:Error-First Callbacks is a convention in Node.js for handling asynchronous operations.They are called Error-First Callbacks because the first argument of a callback function is reserved for an error object

### Q4: How to handle errors using Promises ?

**Answer**: .catch() method is used in Promises for error handling 

### Q5: How to handle errors while using async-await ?

 **Answer**: try-catch block is used with async-await for handling errors

