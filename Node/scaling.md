# Scaling Questions

### Q1: How can node scale to handle 1000s of requests per second 

**Answer**: Following are the ways node can scale to handle 1000's of requests per second 

1. non blocking i/o
2. event driven architecture
3. asynchronous programming
4. Cluster module 

### Q2: Node is single threaded or multithreaded ? 

**Answer**: Node is single threaded 

### Q3: If Node is single threaded how can it handle 1000's of requests per second ? 

**Answer**: Following are the ways Node scales to handle 1000's ofv requests per second 

1.  non blocking i/o
2. event driven architecture
3. asynchronous programming
4. cluster module 

### Q4: What is a fork in node ? 

**Answer**: fork creates a new Node.js process 

```javascript
const { fork } = require("child_processes");

const processes = [

  fork("./app.js", ["3001"]),

  fork("./app.js", ["3002"]),

  fork("./app.js", ["3003"]),

];
```

### Q5: What are the essential differences between fork and spawn ? 

**Answer**: Following are the major differences between fork and spawn 

| Feature                             | fork()                       | spawn()                                    |
| ----------------------------------- | ---------------------------- | ------------------------------------------ |
| purpose                             | creates a new node.js proces | create a new process to run any executable |
| inter process communication channel | yes                          | No                                         |
| Executable types                    | javascript files             | any executable file                        |

