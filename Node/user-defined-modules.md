# Modules(user-defined)

### Q1: What is a module ? 

**Answer**: A module is an encapsulated and reusable chunk of code that has its own context.In node each file is treated as a seperate module 

### Q2: What are the various types of module ? 

**Answer**: The following are the various types of module

1. local modules :- modules we create in our application
2. Built-in-modules :- modules that node.js ships with out of the box
3. Third Party Modules :- Modules written by other developers that we can use in our application

### Q3: What is the relation between CommonJS and Node ? 

**Answer**: CommonJS is a standard that states how a module should be structured and shared .Node adopted CommonJS when it started out

### Q4: How does a module achieve private scoping ? 

**Answer**: 

- Each loaded module in Node is wrapped with an IIFE that provides private scoping of code .
- IIFE helps top-level variables scoped to the module rather than the global object

### Q6: The iife that wraps every module contains 5 properties , What are those 5 properties ? 

**Answer**: The 5 properties are as following :

1. __dirname
2. __filename
3. require
4. exports
5. module

### Q7: What are the 5 patterns of import-export patterns in Common JS ? 

**Answer**: The following code snippet highlights the 5 patterns of import-export patterns in CommonJS

```javascript
//Patten 1

const add = (a, b) => {

return a + b;

};

module.exports = add;

//Pattern 2

module.exports.add = (a, b) => {

return a + b;

};

//Pattern 3

exports.add = (a, b) => {

return a + b;

};

//Pattern 4

const add = (a, b) => {

return a + b;

};

const substract = (a, b) => {

return a - b;

};

module.exports = { add, substract };

//Pattern 5

module.exports.add = (a, b) => {

return a + b;

};

module.exports.substract = (a, b) => {

return a - b;

};

//Pattern 6

exports.add = (a, b) => {

return a + b;

};

exports.substract = (a, b) => {

return a - b;

};


```

### Q8: module.exports vs exports 

**Answer**: From a module node only returns module.exports and not the exports object , exports is just a reference to module.exports , If we directly assign a value or function like exports={} its linkage with module.exports is broken  and exports wont correspond to the module.exports  

### Q9: What are ESModules ? 

**Answer**: Following are the important points about ESModules 

- At the time Node.js was created there was no built-in module system in Javascript
- Node.js defaulted to CommonJS as its module system
- As of 2015 ,Javascript does have a standardized module system as part of the language itself
- That module system is called EcmaScript Modules or ESModule or ESM in short

### Q10: What are the 3 patterns of default exports ? 

**Answer**: Following are the 3 patterns of default exports 

```javascript
//Pattern 1

const add = (a, b) => {

  return a + b;

};

export default add;

import add from "./math-esm.mjs";

console.log(add(5, 5));

//Pattern 2

export default (a, b) => {

  return a + b;

};

import add from "./math-esm.mjs";

console.log(add(5, 5));

//Pattern 3

const add = (a, b) => {

  return a + b;

};

const substract = (a, b) => {

  return a - b;

};

export default {

  add,

  substract,

};

import math from "./math-esm.mjs";

const { add, substract } = math;
```

### Q11: Show a named exports ?

```javascript
export const add = (a, b) => {

  return a + b;

};

export const substract = (a, b) => {

  return a - b;

};

import * as math from "./math-esm.mjs";

const { add, substract } = math;
```

