# REST API-HTTTP Methods And Status Codes

### Q1: What are HTTP verbs or HTTP methods ? 

**Answer**: HTTP methods , also known as HTTP verbs are a *set of actions that a client can take on a resource*

### Q2: What are GET,POST,PUT and DELETE methods ? 

**Answer**: The following table describes the difference between GET,POST,PUT and DELETE 

| HTTP Method | Action                                    |
| ----------- | ----------------------------------------- |
| GET         | *Retreive data from a specified resource* |
| POST        | *submit data* to be processed             |
| PUT         | *update a resource*                       |
| DELETE      | *removal of a resource*                   |

### Q3: PUT vs PATCH 

**Answer**: The answer is explained in the following table 

| PUT                                                          | PATCH                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| In a PUT request the client sends the *full updated resource* in the request body , replacing the existing resource on the server | In a PATCH request , the client sends *specific changes*  updating *only certain fields* without sending the entire resource |



### Q4: Explain the concept of idempotence in Restful APIs

**Answer**: Idempotence means *performing an operation multiple times should have the same outcome as performing it once*.For example sending *multiple GET requests* will always return the same value

### Q5: What are the roles of status codes in Restful APIs ? 

**Answer**: status codes are used to *convey the result of a clients request* 

### Q6: Status codes and their meanings 

**Answer**: Following are the status codes and their meanings 

| status codes | Meanings       |
| ------------ | -------------- |
| 1xx          | *info*         |
| 2xx          | *success*      |
| 3xx          | *redirection*  |
| 4xx          | *client error* |
| 5xx          | *server error* |



