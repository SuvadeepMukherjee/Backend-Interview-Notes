# Event Loop Guess the output Questions 

### Q1: How the event loop Works ? 

**Answer**: Within the event loop , the sequence of execution follows certain rules .

1. Any callbacks in the microtask queue are executed. First, tasks in the nextTick queue and only then tasks in the promise queue.
2. All callbacks within the timer queue are executed.
3. Callbacks in the microtask queue (if present) are executed after every callback in the timer queue. First, tasks in the nextTick queue, and then tasks in the promise queue.
4. All callbacks within the I/O queue are executed.
5. Callbacks in the microtask queues (if present) are executed, starting with nextTickQueue and then Promise queue.
6. All callbacks in the check queue are executed.
7. Callbacks in the microtask queues (if present) are executed after every callback in the check queue. First, tasks in the nextTick queue, and then tasks in the promise queue.
8. All callbacks in the close queue are executed.
9. For one final time in the same loop, the microtask queues are executed. First, tasks in the nextTick queue, and then tasks in the promise queue.

If there are more callbacks to be processed at this point, the loop is kept alive for one more run, and the same steps are repeated. On the other hand, if all callbacks are executed and there is no more code to process, the event loop exits.

![event-loop](../assets/event-loop.webp)

### Q2:Explain the Asynchronous Code Execution of the below code snippet ? 

```javascript
const fs = require("fs");

console.log("First");

fs.readFile(__filename, () => {

  console.log("Second");

});

console.log("Third");
```

**Answer**: The main thread of execution always starts in the global scope. The global function is pushed onto the stack. Execution then comes to line 1. At 1ms, "First" is logged in the console, and the function is popped off the stack. Execution then moves on to line 3. At 2ms, the readFile method is pushed onto the stack. Since readFile is an asynchronous operation, it is off-loaded to libuv.

JavaScript pops off the readFile method from the call stack because its job is done as far as the execution of line 3 is concerned. In the background, libuv starts to read the file contents on a separate thread. At 3ms, JavaScript proceeds to line 7, pushes the log function onto the stack, "Third" is logged to the console, and the function is popped off the stack.

At about 4ms, let's say that the file read task is completed in the thread pool. The associated callback function is now executed on the call stack. Within the callback function, the log statement is encountered.

That is pushed to the call stack, "Second" is logged to the console, and the log function is popped off. As there are no more statements to execute in the callback function, it is popped off as well. There's no more code to run, so the global function is also popped off the stack.

The console output is going to read "First", "Third", and then "Second".

### Experiment 1: Guess the output of below code snippet ? 

```javascript
console.log("console.log 1");

process.nextTick(() => console.log("this is process.nextTick 1"));

console.log("console.log 2"); 
```

**Answer**: The output will be *console.log 1 this is process.nextTick 1 console.log 2*

### Experiment 2 : Guess the output of below code snippet ? 

```javascript
Promise.resolve().then(() => console.log("this is Promise.resolve 1"));

process.nextTick(() => console.log("this is process.nextTick 1"));
```

**Answer**: The output will be `this is process.nextTick 1 this is Promise.resolve 1`