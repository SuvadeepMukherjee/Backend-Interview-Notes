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

//define a route for handling get requests on "/""

app.get("/", (req, res, next) => {

  res.send("Hello World");

});

//define a routes for handling post requests on "/login"

app.post("/login", (req, res, next) => {

  res.send("login Succesfull")

});

app.listen(3000, () => {

  console.log("Server running on port 3000");

});
```

### Q4: What are route handlers ? 

**Answer**:

functions that are responsible for handling requests to specific endpoints (routes) in an application ,in the below code snippet route handler is the *second argument passed* to app.get() or app.post() 

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

### Q5: What are route parameters in express ? 

**Answer**:The following are the salient points about route parameters 

1. route parameters in express.js allow us to *capture dynamic values from the url paths*
2. route parameters can be accessed by using `req.params` object

```javascript
const express = require("express");

const app = express();

app.get("/users/:userId", (req, res, next) => {

  const userId = req.params.usersId;

  res.send(`User id : ${userId}`)

});

app.listen(3000, () => {

  console.log("Server running on port 3000");

});
```

### Q6: What are router object ?

**Answer**:The router object is a *mini version of an express application which is used for handling routes*  

### Q7: Write 4  router methods ? 

**Answer**: `router.get()` ,` router.post()` , `router.put()` , `router.delete()`

### Q9: What is route chaining ? 

**Answer**: route chaining is a process of *defining multiple route handlers for a single route* 

### Q10: What is route nesting ? 

**Answer**: route nesting *organize routes hierarchically by grouping related routes under a common prefix*