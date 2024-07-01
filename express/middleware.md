# Middleware Questions

### Q1: What is middleware in Express.js ? 

**Answer**:a middleware in express.js is a function that handles HTTP requests .It can modify the request or end the request-response cycle

### Q2:  Implement an application level middleware in Express.js that logs to the console "Midlleware executed"

**Answer**: The following code snippet implements an application level middleware 

```javascript
//Initialize an Express application

const express = require("express");

const app = express();

//Define middleware function

const myMiddleware = (req, res, next) => {

  res.send("Hello World");

  next();

};

//Use middleware globally for all users

app.use(myMiddleware);

//Start the server

app.listen(3000, () => {

  console.log("Server is running on port 3000");

});
```

### Q3: What is the purpose of the app.use() function in express ? 

**Answer**: The app.use() method is used to execute (mount) middleware functions gloabally 

### Q4: What is the purpose of the next parameter in express.js 

**Answer**: The next parameter is a callback function which is used to pass control to the next middleware function in the stack 

### Q5: Implement a  middleware globally for a specific route 

**Answer**: use app.use(”/specificRoute”,myMiddleware) to use middleware globally for a specific route in express.js

```javascript
//Initialize an Express application

const express = require("express");

const app = express();

//Define middleware function

const myMiddleware = (req, res, next) => {

  res.send("middleware for specific route");

  
};

//Use middleware globally for all users

app.use("/example", myMiddleware);

//Start the server

app.listen(3000, () => {

  console.log("Server is running on port 3000");

});
```

### Q6: What is request pipeline in express ? 

**Answer**: The request pipeline in express.js is a series of middleware functions that handle incoming HTTP requests and pass control to the next function 

![request-pipeline](../assets/request-pipeline.png)

### Q7: What are the types of middleware in express.js 

**Answer**: The following are the various types of middleware in express.js

1. Application-level middleware
2. Router-level middleware
3. Error-handling middleware
4. Built in middleware
5. Third party middleware

### Q8: What is the difference between application-level and route-level middleware ? 

**Answer**: application-level middleware applies globally to all incoming requests in the entire express.js applications. route-level middleware applies only to specific routes , not all incoming requests

### Q9: What is error handling middleware and how to implement it ? 

**Answer**: error handling middleware in express is a special kind of middleware used to manage errors happening while handling incoming requests , to implement error handling in express define middleware with 4 parameters (err,req,res,next) ,here the additional error object parameter will be used for error handling 

```javascript
app.use((err, req, res, next) => {

  console.error(err.stack);

  res.status(500).send("Something went wrong");

});
```

### Q10: If you have 5 middleware then in which middleware you will do the error handling ? 

**Answer**:In case of multiple middleware , error handling middleware should be defined at last(after all other middleware) because when an error occurs Express.js will search for the next error-handling middleware skipping any regular middleware or route handler 

### Q11: What is built in middlewares  ? How to serve static files from Express.js 

**Answer**:built in middlewares are built in functions inside express framework which provide common functionalities .express.static() middleware is used for serving static files 

```javascript
const express = require("express");

const app = express();

//serve static files from the public folder

app.use(express.static("public"));
```

### Q12: What are third party middlewares ? Give some examples 

**Answer**: Third party middleware in express.js are modules developed by third party developers (not part of core express.js) 

| third party middleware | what purpose they serve ? |
| ---------------------- | ------------------------- |
| Morgan                 | Logging                   |
| Helmet                 | Security                  |
| Body-parser            | body parsing              |
| Compression            | Compression               |

### Q13: Types of middleware 

**Answer**:The various types of middleware are explained in the follwing table 

| Middleware                   | Purpose                                                      |
| ---------------------------- | ------------------------------------------------------------ |
| application-level middleware | Middleware applied to all routes                             |
| Router-level-middleware      | Middleware specific to certain routes                        |
| Built-in-middleware          | pre-packaged middleware included with express.js , like for serving static files |
| Error-handling middleware    | middleware for handling errors , declared after other middleware , triggered on errors |

 

### Q14: Advantages of using middleware in express.js 

**Answer**: The following are the advantages of using middleware 

1. Modularity ⇒ middleware allows us to modularize our applications functionality into smaller, self-contained units .Each middleware function can handle a specific task or concern such as logging,authentication or error-handling
2. Reusability ⇒ middlewares can be reused at multiple places and that makes application code easier to maintain
3. Improved request handling ⇒ middlewares functions have access to both the request(req) and response(res) objects which enables us to perform validations on request or modify the response before sending it back to the client
4. Flexible control flow ⇒ middleware functions can be applied globally to all routes or selectively to specific routes allowing us to control the flow of request processing to our application
5. Third party middlewares ⇒ express.js offers a wide range of third party middleware packages that provide additional functionality eg-body-parser,cors