# 1️⃣ What is Node.js?
Node.js is a JavaScript runtime environment that allows you to run JavaScript outside the browser, mainly on the server-side.
It is built on Chrome’s V8 engine and is used to build fast, scalable backend applications.

# 2️⃣ Is Node.js single-threaded?
👉 Yes, Node.js is single-threaded for executing JavaScript.
But 👇
- It uses multiple background threads (via libuv) for tasks like:
   - File system
   - Network calls
   - Timers
So Node is single-threaded + asynchronous.

# 3️⃣ How does Node.js handle multiple requests?
Node.js uses:
 - Event Loop
 - Non-blocking I/O
 - Asynchronous callbacks
Instead of waiting for one request to finish, Node:
 1 Receives request
 2 Sends heavy work to background
 3 Continues handling other requests
 4 Executes callback when task completes
👉 This makes Node very fast.

# 4️⃣ What is V8 Engine?
V8 is:
 - Google’s JavaScript engine
 - Written in C++
 - Converts JavaScript into machine code
Node.js uses V8 to execute JS code very fast.

# 5️⃣ What is Event Loop?
The Event Loop continuously checks:
 - Call Stack
 - Callback Queue
 - Microtask Queue
It decides when and which function should execute next.
👉 It is the heart of Node.js asynchronous behavior.

# ✅ EVENT LOOP & ASYNC
6️⃣ What is a Callback?
A callback is a function passed as an argument to another function and executed later.
Example:

```
fs.readFile("file.txt", () => {
  console.log("File read");
});
```
# 7️⃣ What is Callback Hell?
Callback hell happens when:
 - Too many nested callbacks
 - Code becomes unreadable and hard to maintain
Example:
```
a(() => {
  b(() => {
    c(() => {
      d();
    });
  });
});
```
# 8️⃣ Promise vs async/await
| Promise                  | async/await                 |
| ------------------------ | --------------------------- |
| `.then()` and `.catch()` | Looks like synchronous code |
| Harder to read           | Easier to understand        |
| Older style              | Modern approach             |

Example:
```
// Promise
fetch().then().catch();

// async/await
try {
  await fetch();
} catch (e) {}
```
# 9️⃣ Microtask Queue vs Macrotask Queue
| Microtask Queue   | Macrotask Queue           |
| ----------------- | ------------------------- |
| Promise callbacks | setTimeout, setInterval   |
| Executed first    | Executed after microtasks |
| Faster priority   | Lower priority            |

👉 Order:
Call Stack → Microtask → Macrotask
# 🔟 What is Non-blocking I/O?
Non-blocking I/O means:
 - Node does not wait for I/O tasks
 - It continues executing other code

Example:

```
fs.readFile() // non-blocking
```

# 1️⃣ What is Middleware?
Middleware is a function that runs:
  - Before request reaches controller
   - Between request & response
Used for:
   - Authentication
   - Logging
   - Validation

Example:
```
app.use((req, res, next) => {
  console.log("Middleware");
  next();
});
```
# 12️⃣ What is REPL?
REPL stands for:
 - Read
 - Evaluate
 - Print
 - Loop
It is an interactive Node shell used for testing code.

Command:
```
node
```

# 13️⃣ What is Stream?
Streams handle large data efficiently by processing it in chunks.
Types:
 - Readable
 - Writable
 - Duplex
 - Transform

Example:
```
fs.createReadStream("file.txt");
```
# 14️⃣ What is Buffer?
Buffer is used to handle binary data directly in memory.

Example:
```
const buf = Buffer.from("Hello");
```
Used in:
File handling
Streams
Network data

# 15️⃣ What is Clustering?
Clustering allows Node to:
 - Use multiple CPU cores
 - Create multiple worker processes
Improves:
  - Performance
  - Scalability
✅ SECURITY & PERFORMANCE
# 16️⃣ How to secure a Node.js app?
 - Use HTTPS
 - Hash passwords using bcrypt
 - Use JWT for authentication
 - Validate inputs
 - Use Helmet for security headers
 - Hide secrets using .env

# 17️⃣ What is Rate Limiting?
Rate limiting restricts:
 - Number of requests per user/IP
Used to prevent:
 - DDoS attacks
 - API abuse
Example:
