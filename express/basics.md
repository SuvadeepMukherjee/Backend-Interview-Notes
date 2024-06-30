# Basic Questions 

### Q1:What are the advantages of using Express.js with Node.js 

**Answer**: The following are the advantages of using express

1. Simplilfied web development : express.js provides a lightweight framework that simplifies the process of building web applications in node.js
2. Middleware Support: easy integration of middleware functions into applications request-response cycle
3. Flexible Routing System : defining routes for handling different HTTP methods (GET,POST,PUT,DELETE etc) and url patterns is easy
4. Template Engine Integration: express.js supports various template engines making it easy to generate dynamic HTML content on the server side

### Q2:How do you install express 

**Answer**: `npm install express`

### Q3: How to create a HTTP server using express.js 

**Answer**: The following code snippet explains how to create a web server with express 

```javascript
const express = require("express");

const app = express();

app.listen(3000, () => {

  console.log("Server is running on port 3000");

});
```

