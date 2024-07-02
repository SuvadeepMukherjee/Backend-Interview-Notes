# ORM-ODM Questions 

### Q1:What is sequelize ? 

**Answer**:sequelize is a node.js *object relational mapping library* for relational databases 

### Q2: What are the different types of relations in SQL and how to implement them in sequelize  ? 

**Answer**: There are 3 different types of relations in sql , they are : 

1. One-to-One(1:1)
2. One-to-Many(1:N)
3. Many-to-Many(N:M)

To implement these relations with Sequelize : 

1. `One-to-One` : Define associations using `hasOne` and `belongsTo` methods 
2. `One-to-Many`: Define associations  using `hasMany` and `belongsTo`
3. `Many-to-Many`: Define associations using `belongsToMany`

### Q3: How to connect sequelize to database ? 

```javascript
const Sequelize = require("sequelize");

const sequelize = new Sequelize(

  process.env.DB_NAME,

  process.env.DB_USER,

  process.env.DB_PASSWORD,

  {

​    dialect: "mysql",

​    host: process.env.DB_HOST,

  }

);

module.exports = sequelize;
```

