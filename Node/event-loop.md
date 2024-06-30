# Event Loop Questions

### Q1: "javascript is a synchronous , blocking , single-threaded language" Is the above statement correct ? 

**Answer**: yes 

### Q2: Draw a picture of the Node.js runtime ? 

**Answer**: 

![](/Users/suvadeep/Desktop/Screenshot 2024-06-30 at 8.48.10 PM.png)

- **External dependencies** — such as V8, libuv, crypto — required by Node.js for its functioning
- **C++ features** that provide for functionality such as file system access and networking
- A **JavaScript library** that provides functions and utilities to tap into the C++ features from your JavaScript code