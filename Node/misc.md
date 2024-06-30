# Misc Questions

### Q1: What is the use of package.json file ? 

**Answer**: The package.json file in a Node.js project is used to manage project metadata, dependencies, and scripts, ensuring consistent  project configuration and facilitating package management.

### Q2: What is the use of packagelock.json file ? 

**Answer**:  The package-lock.json file ensures consistent installations by locking the exact versions of dependencies, providing a reliable and reproducible build.

### Q3: Flags used in read/write operations in files 

**Answer**: Following are the commonly used flags in read/write operations 

| Flag | Description                                                  |
| ---- | ------------------------------------------------------------ |
| r    | Opens a file for reading. The file must exist.               |
| w    | Opens a file for writing. Creates a new file if it does not exist or truncates the file if it exists. |
| a    | Opens a file for appending. Data will be added to the end of the file. Creates a new file if it does not exist. |

### Q4: node_env 

**Answer**: Following are the various node environments 

| Value       | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| Development | Enables detailed logging, hot-reloading, and other development tools. |
| Production  | Optimizes performance, disables detailed logs, and applies security measures. |
| Test        | Uses test-specific configurations like mock services and test databases. |

The NODE_ENV variable helps configure the application for different environments to ensure proper behavior and performance.

### Q5: Explain the MVC architecture ? 

**Answer**: The MVC architecture is described in the follwing table 

| Component   | Role                                                         |
| ----------- | ------------------------------------------------------------ |
| Models      | Represent the data structure and business logic. Handle data retrieval, storage, and validation. |
| Views       | Define the presentation layer. Render the user interface and display data from the model to the user. |
| Controllers | Handle user input and interactions. Update the model and select the appropriate view for response. |

### Q6: What is npm ? 

**Answer**: npm is used to manage the dependencies for our node project 