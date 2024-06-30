Notes:
https://boulder-earwig-bb4.notion.site/Node-79031dbc909f4e0892b09b1de44cb5f0?pvs=4

# Basics 



## What is the difference between realtive path and absolute path ? 

- Relative path: Specifies the location of a file or directory *relative* to the current working directory.
- Absolute path: Specifies the *complete path* of a file or directory from the root directory of the file system.

## Create a server with Node ? 

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

## What do you mean by Node.js Event driven architecture ? 

event emitters emit events , These events are picked by event listeners which fires off callback functions attached to each event listen 

