# REST API -CORS,Serialization,Desrialization,Others

### Q1: What is CORS in Restful APIs ? 

**Answer**: CORS(Cross Origin Resource Sharing) is a *security feature* implemented in web browsers that *restrict web pages or scripts from making requests to a different domain than the one that served the web page*

### Q2: How to remove CORS restrictions in RESTful APIs 

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

### Q3: What is Serialization and Deserialization ? 

**Answer**:The following table explains the difference between Serialization and Deserialization

| Serialization                                                | Deserialization                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Serialization is the process of *converting an object into a format that can be stored,transmitted or reconstructyed later(json)* | Deserialization is the process of converting *serialized data such as binary/xml/json data back into an object* |



### Q4: what are the types of Serialization 

**Answer**:The following are the 3 types of serialization 

1. *Binary Serialization*
2. *XML Serialization*
3. *JSON Serialization*

### Q5: How to Serialize in Node ? 

**Answer**: Serialize a Javascript object into JSON format using `JSON.stringify()`

```javascript
//Serialization (to JSON)

const obj = { name: "Suvadeep", age: 32 };

const jsonStr = JSON.stringify(obj);

console.log("Serialized JSON:", jsonStr);


```

### Q6: How to Deserialize in Node.js

**Answer**: Deserialize a JSON string into a Javascript object using `JSON.parse()`

```javascript
//Deserialization (to JSON)

const jsonStr2 = "{name:'Suvadeep',age:32}";

const obj2 = JSON.parse(jsonStr2);

console.log("Deserialized JSON", obj2);
```

### Q7: Explain the concept of versioning in RESTful APIs ? 

**Answer**: Versioning  in RESTful APIs refer to the practise of maintaining multiple versions of an API to support backward compatibility  

### Q8: What is an API document ? What are some popular documentation formats ? 

**Answer**: An API document , describe the functionality deatures and usage of a REST API

Some popular documentation formats are

1. Swagger(OpenAPI)
2. API blueprint
3. RAML