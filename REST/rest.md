# Rest API Questions

### Q1 : What is REST ? 

**Answer**: REST(Representational State Transfer) is a set of guidelines for creating APIs 

### Q2: What is Restful API ?

**Answer**: service which follows REST guidelines

### Q3: What are top 5 REST guidelines ? 

**Answer**:These are the top 5 REST guidelines:

1. Separation of client and server : The implementation of the client and the server must be done independtly
2. Stateless : The server will not store anything about the latest HTTP request the client made
3. Uniform Interface: Identify the resources by URL
4. Cacheable : The API response should be cacheable to improve the performance
5. Layered System : The system should follow layered pattern ( a layered system such as the Model-View-Controller promotes modular design and seperation of concerns)

### Q4: REST vs SOAP 

**Answer**: The following table describes the difference between REST and SOAP

| Feature        | REST                               | SOAP                                              |
| -------------- | ---------------------------------- | ------------------------------------------------- |
| Architecture   | REST is an architectural style     | SOAP(Simple Object Access Protocol) is a protocol |
| Protocol       | uses HTTP or HTTPS                 | can use various protocols(HTTP,SMTP,etc)          |
| message format | uses light weight format like JSON | typically uses XML                                |
| state          | stateless                          | can be stateful or stateless                      |
| error handling | relies on HTTP status codes        | defines its own fault mechanisms                  |
| performance    | generally lightweight and faster   | can be slower due to XML processing               |

### Q5: What are HTTP verbs or HTTP methods ? 

**Answer**: HTTP methods , also known as HTTP verbs are a set of actions that a client can take on a resource

### Q6: What are GET,POST,PUT and DELETE methods ? 

**Answer**: The following table describes the difference between GET,POST,PUT and DELETE 

| HTTP Method | Action                                                       |
| ----------- | ------------------------------------------------------------ |
| GET         | Retreive data from a specified resource                      |
| POST        | submit data to be processed                                  |
| PUT         | update a resource or create a new resource if it does not exist |
| DELETE      | request removal of a resource                                |

### Q7: PUT vs PATCH 

**Answer**: PUT(Full Resource Replacement) ⇒ In a PUT request the client sends the full updated resource in the request body , replacing the existing resource on the server

PATCH(Partial Updates) ⇒ In a PATCH request , the client sends specific changes or instructions for modifying the resouce , updating only certain fields without sending the entire resource

### Q8: Explain the concept of idempotence in Restful APIs

**Answer**: Idempotence means performing an operation multiple times should have the same outcome as performing it once.For example sending multiple GET requests will always return the same value

### Q9: What are the roles of status codes in Restful APIs ? 

**Answer**: status codes are used to convey the result of a clients request 

### Q10: Status codes and their meanings 

**Answer**: Following are the status codes and their meanings 

| status codes | Meanings     |
| ------------ | ------------ |
| 1xx          | Info         |
| 2xx          | success      |
| 3xx          | redirection  |
| 4xx          | client error |
| 5xx          | server error |

### Q11: What is CORS in Restful APIs ? 

**Answer**: CORS(Cross Origin Resource Sharing) is a security feature implemented in web browsers that restrict web pages or scripts from making requests to a different domain than the one that served the web page

### Q12: How to remove CORS restrictions in RESTful APIs 

**Answer**: CORS restrictions can be removed by enabling CORS middleware in application

```javascript
const express = require("express");

const cors = require("cors");

const app = express();

//enable CORS middleware for all routes

app.use(cors());

//optionally configure cors to allow requests from specific origins

//now cors will allow requests from discord.com

app.use(

  cors({

​    origin: "https://discord.com",

  })

);
```

### Q13: What is Serialization and Deserialization ? 

**Answer**:Serialization is the process of converting an object into a format that can be stored,transmitted or reconstructyed later(json)

Deserialization is the process of converting serialized data such as binary/xml/json data back into an object

### Q14: what are the types of Serialization 

**Answer**:The following are the 3 types of serialization 

1. Binary Serialization
2. XML Serialization
3. JSON Serialization

### Q15: How to Serialize in Node ? 

**Answer**: Serialize a Javascript object into JSON format using JSON.stringify()

```javascript
//Serialization (to JSON)

const obj = { name: "Suvadeep", age: 32 };

const jsonStr = JSON.stringify(obj);

console.log("Serialized JSON:", jsonStr);


```

### Q16: How to Deserialize in Node.js

**Answer**: Deserialize a JSON string into a Javascript object using JSON.parse()

```javascript
//Deserialization (to JSON)

const jsonStr2 = "{name:'Suvadeep',age:32}";

const obj2 = JSON.parse(jsonStr2);

console.log("Deserialized JSON", obj2);
```

### Q17: Explain the concept of versioning in RESTful APIs ? 

**Answer**: Versioning  in RESTful APIs refer to the practise of maintaining multiple versions of an API to support backward compatibility  

### Q18: What is an API document ? What are some popular documentation formats ? 

**Answer**: An API document , describe the functionality deatures and usage of a REST API

Some popular documentation formats are

1. Swagger(OpenAPI)
2. API blueprint
3. RAML

### Q19: What are Authentication and Authorization ? 

**Answer**: Authentication is the process of verifying the identity of a user by validating their credentials such as username and password

Authorization is the process of allowing an authenticated user access to resources .Authentication is always precedes to Authorization

### Q20: 5 types of Authentication 

**Answer**:The following are the various types of authentication

1. Basic(Username and Password) Authentication
2. API Key Authentication
3. Token-based Authentication(JWT)
4. Multi-factor Authentication(MFA)
5. Certificate-based Authentication

### Q21: What is Basic Authentication ? 

**Answer**:In Basic Authentication , the user passes their credentials on a post request . At the Node Rest API-end , credentials are verified and response is sent back .The disdavantage of it is Basic Authentication sends credentials in plain text over the network , so it is not considered a secure method of authentication

### Q22: What are the security risks associated with storing passwords in plain text in Node.js

**Answer**:Storing passwords in plain text means that anyone with access to the storage location , such as a database ocan easily read and extract passwords

### Q23:What is the role of Hashing and Salt in securing passwords ? 

**Answer**:Hashing is the process of converting a password into a fixed-size string of characters using a mathematical algorithm , We generate salt by using bcrypt library (random string) 

### Q24: What is API Key Authentication ? 

**Answer**: In API Key Authentication , the API owner will share an API key with the users and this key will authenticate the users of that API 