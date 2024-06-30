# REST API - Authentication And Authorization

### Q1: What are Authentication and Authorization ? 

**Answer**: Authentication is the process of verifying the identity of a user by validating their credentials such as username and password

Authorization is the process of allowing an authenticated user access to resources .Authentication is always precedes to Authorization

### Q2: 5 types of Authentication 

**Answer**:The following are the various types of authentication

1. Basic(Username and Password) Authentication
2. API Key Authentication
3. Token-based Authentication(JWT)
4. Multi-factor Authentication(MFA)
5. Certificate-based Authentication

### Q3: What is Basic Authentication ? 

**Answer**:In Basic Authentication , the user passes their credentials on a post request . At the Node Rest API-end , credentials are verified and response is sent back .The disdavantage of it is Basic Authentication sends credentials in plain text over the network , so it is not considered a secure method of authentication

### Q4: What are the security risks associated with storing passwords in plain text in Node.js

**Answer**:Storing passwords in plain text means that anyone with access to the storage location , such as a database ocan easily read and extract passwords

### Q5:What is the role of Hashing and Salt in securing passwords ? 

**Answer**:Hashing is the process of converting a password into a fixed-size string of characters using a mathematical algorithm , We generate salt by using bcrypt library (random string) 

### Q6: What is API Key Authentication ? 

**Answer**: In API Key Authentication , the API owner will share an API key with the users and this key will authenticate the users of that API 