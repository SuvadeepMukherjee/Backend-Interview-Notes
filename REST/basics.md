# REST API-Basics

### Q1 : What is REST ? 

**Answer**: REST aka *Representational State Transfer* is a *set of guidelines for creating APIs* 

### Q2: What is Restful API ?

**Answer**: api which follows *REST guidelines*

### Q3: What are top 5 REST guidelines ? 

**Answer**:These are the top 5 REST guidelines:

1. *Separation of client and server* : The implementation of the client and the server must be done independtly
2. *Stateless* : The server will not store anything about the latest HTTP request the client made
3. *Uniform Interface*: Identify the resources by URL
4. *Cacheable* : The API response should be cacheable to improve the performance
5. *Layered System* : The system should follow layered pattern ( a layered system such as the *Model-View-Controller* promotes modular design and seperation of concerns)

### Q4: REST vs SOAP 

**Answer**: The following table describes the difference between REST and SOAP

| Feature        | REST                                 | SOAP                                                |
| -------------- | ------------------------------------ | --------------------------------------------------- |
| Architecture   | REST is an *architectural style*     | SOAP(Simple Object Access Protocol) is a *protocol* |
| Protocol       | uses *HTTP or HTTPS*                 | can use *various protocols*(HTTP,SMTP,etc)          |
| message format | uses light weight format like *JSON* | typically uses *XML*                                |
| state          | *stateless*                          | can be *stateful or stateless*                      |
| error handling | relies on *HTTP status codes*        | defines its *own fault mechanisms*                  |
| performance    | generally *lightweight and faster*   | can be *slower due to XML processing*               |