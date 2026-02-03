# What is Node.js?
- Node.js is a JavaScript runtime built on Chrome’s V8 engine
- Used to build backend / server-side applications
- It is asynchronous and non-blocking

# Why Node.js?
- Fast 🚀
- Single language (JS for frontend + backend)
- Handles multiple requests efficiently

# Install Node.js
Check version:
```
node -v
npm -v
```
Your first Node.js program
Create app.js
```
console.log("Hello Node.js");
```
Run:
```
node app.js
```
# What are Modules?
1. Modules help us divide code into reusable files
2. Types of Modules
3. Built-in (fs, http, path)

Custom
Third-party (express, mongoose)
```
const fs = require("fs");

fs.writeFileSync("test.txt", "Hello File");
```
# Custom Module Example

📁 math.js
```
function add(a, b) {
  return a + b;
}

module.exports = add;
```
📁 app.js
```
const add = require("./math");

console.log(add(2, 3));
```
# What is Express?
- Express is a Node.js framework
- Makes server creation easy

Install Express
```
npm init -y
npm install express
```
Basic Express Server
```
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Hello Express");
});

app.listen(3000, () => {
  console.log("Server running on port 3000");
});
```
Open browser 👉 http://localhost:3000
# What is Routing?
Routing decides which URL → which function

Basic Routes
```
app.get("/home", (req, res) => {
  res.send("Home Page");
});

app.post("/login", (req, res) => {
  res.send("Login Page");
});
```
# Route Parameter:
```
app.get("/user/:id", (req, res) => {
  res.send(req.params.id);
});



```
# What is Middleware?
Middleware runs between request & response
📌 Uses:
- Authentication
- Logging
- Validation

Custom Middleware
```
function logger(req, res, next) {
  console.log("Request received");
  next();
}

app.use(logger);
```
Built-in Middleware
```
app.use(express.json());
```
# What is REST?
REST = Representational State Transfer

HTTP Methods
| Method | Work        |
| ------ | ----------- |
| GET    | Fetch data  |
| POST   | Create data |
| PUT    | Update data |
| DELETE | Remove data |

# REST API Example
```
app.get("/users", (req, res) => {
  res.json({ users: [] });
});

app.post("/users", (req, res) => {
  res.send("User created");
});
```
# What is Postman?
- Tool to test APIs
- Send GET / POST / PUT / DELETE requests

Example
- URL: http://localhost:3000/users
- Method: GET

📌 Used to test backend without frontend
# What is MVC?

MVC = Model – View – Controller

| Layer      | Work           |
| ---------- | -------------- |
| Model      | Database logic |
| View       | UI             |
| Controller | Business logic |

# MVC Folder Structure
```
project/
 ├── controllers/
 ├── routes/
 ├── models/
 ├── app.js
```
# Controller Example
```
exports.getUsers = (req, res) => {
  res.send("Users List");
};
```
# Basic Error Handling
```
app.use((err, req, res, next) => {
  res.status(500).send("Something went wrong");
});
```
# Try-Catch
```
app.get("/", (req, res) => {
  try {
    throw new Error("Error");
  } catch (err) {
    res.send(err.message);
  }
});
```
# What is Validation?
- Check user input is correct
- Prevent wrong data

Manual Validation
```
app.post("/register", (req, res) => {
  const { email } = req.body;

  if (!email) {
    return res.status(400).send("Email required");
  }

  res.send("Success");
});
```
Using express-validator
```
npm install express-validator
```
```
const { body, validationResult } = require("express-validator");

app.post("/login",
  body("email").isEmail(),
  (req, res) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
      return res.status(400).json(errors.array());
    }
    res.send("Login success");
  }
);
```
# 1. Node.js
What is Node.js?

Node.js is an open-source, cross-platform JavaScript runtime environment that allows developers to run JavaScript code on the server side. It is built on Google Chrome’s V8 JavaScript engine.

# Key Features of Node.js
- Asynchronous & Non-Blocking I/O
- Single-threaded but highly scalable
- Fast execution
- Event-driven architecture
- Uses JavaScript for backend development

# Advantages of Node.js
- High performance
- Handles multiple client requests efficiently
- Same language for frontend and backend
- Large ecosystem via npm (Node Package Manager)

# 2. Modules in Node.js
What are Modules?

Modules are reusable blocks of code that help in organizing an application into smaller, manageable files.

# Types of Modules
1. Built-in Modules – fs, http, path
2. Custom Modules – User-defined modules
3. Third-party Modules – Express, Mongoose

# Benefits of Modules
- Code reusability
- Better maintainability
- Improved readability

# 3. Express.js
What is Express.js?

Express.js is a lightweight web application framework for Node.js that simplifies the development of web servers and RESTful APIs.

# Why Use Express?
- Simple and flexible
- Faster development
- Easy routing and middleware support
- Widely used in industry

# 4. Routing in Express.js
What is Routing?

Routing defines how an application responds to client requests for specific URLs and HTTP methods.

# Types of Routing
- GET Routing – Fetch data-
- POST Routing – Send data
- PUT Routing – Update data
- DELETE Routing – Remove data

Routing helps in structuring the application and handling different API endpoints.  

# 5. Middleware in Express.js
What is Middleware?

Middleware functions are functions that execute between the request and response cycle in an Express application.

# Uses of Middleware
- Authentication and authorization
- Logging requests
- Parsing request bodies
- Error handling
Middleware improves application control and security.

# 6. REST API
What is REST?

REST (Representational State Transfer) is an architectural style used for designing stateless and scalable web services.

# REST Principles
- Client-Server architecture
- Stateless communication
- Uniform interface
- Resource-based URLs

# Common HTTP Methods
- GET – Retrieve data
- POST – Create data
- PUT – Update data
- DELETE – Delete data

7. Postman
What is Postman?

Postman is an API testing tool used to send requests and analyze responses without a frontend.

# Importance of Postman
- API testing
- Debugging backend logic
- Faster development and validation

# 8. MVC Architecture
What is MVC?

MVC stands for Model-View-Controller, a design pattern used to separate application logic.

# Components of MVC
- Model – Handles database and data logic
- View – User interface
- Controller – Business logic and request handling

# Benefits of MVC
- Clean code structure
- Easy maintenance
- Better scalability

# 9. Error Handling
What is Error Handling?

Error handling is the process of managing runtime and logical errors to prevent application crashes.

# Importance of Error Handling
- Improves application stability
- Provides meaningful error messages
- Helps debugging issues

Express provides centralized error-handling middleware.

# 10. Validation
What is Validation?

Validation ensures that user input data is correct, complete, and secure before processing.

# Importance of Validation
- Prevents invalid data
- Enhances security
- Maintains data integrity

Validation can be done manually or using libraries like express-validator.


Node.js and Express together provide a powerful backend development environment. By using modules, middleware, REST APIs, MVC architecture, proper error handling, and validation, developers can build scalable, secure, and maintainable web applications, which are widely used in real-world company projects.
  


Built-in Module Example (fs)
