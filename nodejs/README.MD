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
