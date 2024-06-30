Notes:
https://boulder-earwig-bb4.notion.site/Node-79031dbc909f4e0892b09b1de44cb5f0?pvs=4

# Basics 



### Q1: What is the difference between realtive path and absolute path ? 

**Answer**: Following are the differences between relative path and ansolute path 

- Relative path: Specifies the location of a file or directory *relative* to the current working directory.
- Absolute path: Specifies the *complete path* of a file or directory from the root directory of the file system.

### Q2: Create a server with Node ? 

**Answer**: 

```javascript

const http = require("http");

const requestListener = (req, res) => {

res.writeHead(200);

res.send("Hello World");

};

const server = http.createServer(requestListener);

server.listen(3000, () => {

console.log("Server is running on port 3000");

});
```

### Q3: What do you mean by Node.js Event driven architecture ? 

**Answer** ; event emitters emit events , These events are picked by event listeners which fires off callback functions attached to each event listen 

### Q4: What is the observer pattern in Javascript programming ?

**Answer**:event emitter emits events which are picked up by event listeners which fires off callback functions attached to each event listener 

### Q5: What does process.exit() do ? 

**Answer**:terminates the current node process with the specified exit code 

### Q6:When would you use -- save -dev and when would you use -- save

**Answer**: 

-- save - dev to install packages which we need during development like nodemon

-- save to install packages that we need during production like express

### Q6: List 5 advantages of node 

**Answer**: Following are the 5 advantages of Node.js

1. high perfoirmance
2. highly scalable 
3. single language 
4. rich ecosystem
5. real time applications 

### Q7: HTTP Methods 

**Answer**:

| HTTP Methods | Description                                                  |
| ------------ | ------------------------------------------------------------ |
| GET          | requests data from a server                                  |
| POST         | submits data to be processed to a specified resource         |
| PUT          | replaces all current representations of the target resource with the uploaded content |
| DELETE       | deletes the specified resource                               |

### Q8: Which module is used to read and write operations ?

**Answer**: fIlesystem module(fs)

### Q9: How many types of API functions are there in Node ? 

**Answer** :

| Type                           | Description                                                  | Example         |
| ------------------------------ | ------------------------------------------------------------ | --------------- |
| asynchronous , non-blocking    | Operate asynchronously. Node.js doesn’t get blocked while waiting for data. Continues to move to the next API call. | fs.readFile     |
| synchronous blocking functions | Act as blocking functions. Application waits for a response until the value is returned | fs.readFileSync |

