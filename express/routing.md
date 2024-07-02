# Routing Questions

### Q1: What is routing in express ?

**Answer**: routing is the process of *directing incoming http requests to the appropriate handler function based on the request method ( eg GET,POST) and the url path*  

### Q2: What is difference between middleware and routing 

**Answer**: The following table describes the difference between middleware and routing 

| Middleware                                                   | Routing                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| middlewares are functions that have access to request-response cycle , it *can modify the request or end the request-response cycle* | routing is the *process of directing  incoming http requests to the appropriate handler function based on the request method and path* |

### Q3: Define 2 routes 

1. ### GET request on  route "/"  respond with  Hello World 

2. ### POST request on  route "/login" respond with "login Successfull"

**Answer**:The following code snippet describes the way to implement routing in express

```javascript
const express = require("express");

const app = express();

//define a route for handling get requests

app.get("/", (req, res, next) => {

  res.send("Hello World");

});

//define a routes for handling post requests

app.post("/login", (req, res, next) => {

  res.send("login Succesfull")

});

app.listen(3000, () => {

  console.log("Server running on port 3000");

});
```

#### Q4: How to handle routing in express.js real applications ? 

**Answer**:The following are the steps to handle routing in express.js real applications

1. import express
2. set middlewares
3. import controllers
4. define routes for different end points
5. start the server

### Q5: What are route handlers ? 

**Answer**:route handlers is the second argument passed to app.get() or app.post() , route handler function is used to process the request and generate a response 

```javascript
//define a route for handling get requests

app.get("/", (req, res, next) => {

  res.send("Suvadeep");

});

//define a routes for handling post requests

app.post("/login", (req, res, next) => {

  //handle logic

});
```

### Q6: What are route parameters in express ? 

**Answer**:route parameters in express.js allow us to capture dynamic values from the url paths

route parameters can be accessed by using `req.params` object

```javascript
const express = require("express");

const app = express();

app.get("/users/:userId", (req, res, next) => {

  const userId = req.params.usersId;

  res.send("User id : ${userId}")

});

app.listen(3000, () => {

  console.log("Server running on port 3000");

});
```

### Q7: What are router object and router methods ? 

**Answer**:The router object is a mini version of an express application which is used for handling routes , router methods are functions provided by the router object to define routes for different http methods (GET,POST,DELETE,etc) 

### Q8: What are the types of router methods ? 

**Answer**: router.get() , router.post() , router.put() , router.delete()

### Q9: What is the difference between app.get() and router.get() ? 

**Answer**: The following table describes the difference between app.get() and router.get()

| app.get()                                                    | router.get()                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| The app.get() method is used to define routes directly on the application object | The router.get() method is used to define routes on a router object |
| routes defined using app.get() are automatically mounted on the route path | routes defined using router.get() are not automatically mounted , they must be explicitly mounted using app.use() |
| routes defined using app.get() are not modular and cannot be reused in other application | outes defined using router.get()  are not automatically mounted , they must be explcitly mounted using app.use() |

### Q10: What is express.router() in express.js 

**Answer**:express.router() is a class in express.js that returns a new router object 

### Q11: What is route chaining ? 

**Answer**: route chaining is a process of defining multiple route handlers for a single route 

### Q12: What is route nesting ? 

**Answer**: route nesting organize routes hierarchically by grouping related routes under a common prefix