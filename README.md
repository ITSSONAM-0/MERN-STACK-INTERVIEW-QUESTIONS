# 🧩 OVERALL FLOW
```scss
User → React (Frontend) → Node + Express (Backend API)
     → MongoDB (Database)
     ← Response (JSON)
     ← React UI Update
```
# ⚛️ 1️⃣ REACT JS (FRONTEND PROCESS)
Role: User Interface (UI)
# 📌 Process:
1. User browser me website open karta hai
2. React app load hoti hai (components render hote hain)
3. User koi action karta hai
.   👉 login, signup, add to cart, order food
4. React API request bhejta hai backend ko
fetch / axios
GET / POST / PUT / DELETE
5. Response aane par:
state update hota hai
UI automatically re-render hoti hai

# # 🧠 Important Points:
- React sirf data show karta hai
- Direct database access ❌
- Backend se JSON data aata hai


# 🟢 2️⃣ NODE JS (BACKEND RUNTIME)
Role: JavaScript ko server par run karna

# 📌 Process:
1. Node server start hota hai (node index.js)
2. Client (React) se request aati hai
3. Node request ko handle karta hai asynchronously
4. Event loop multiple users ko efficiently handle karta hai

# 🧠 Important Points:
- Non-blocking
- Single-threaded but scalable
- Fast API handling


# 🚀 3️⃣ EXPRESS JS (BACKEND FRAMEWORK)
Role: API banana + routing + middleware

# 📌 Process:
1. Express server request receive karta hai
2. Middleware run hota hai:
  -  body parser
  -  auth (JWT)
  -  ogging
4. Request correct route par jaati hai
  - 👉 /api/login, /api/order
5. Controller function execute hota hai
6. MongoDB se data mangta / save karta hai
7. Response JSON me React ko bhejta hai

# 🧠 Important Points:
- Express = bridge between React & MongoDB
- REST API principles follow karta hai

# 🍃 4️⃣ MONGODB (DATABASE PROCESS)
Role: Data store karna (NoSQL)
# 📌 Process:
1.Express → Mongoose ke through MongoDB se connect
2. Schema define hota hai
 - 👉 User, Order, Product
3. CRUD operations perform hote hain:
 - Create
 - Read
 - Update
 - Delete
4. MongoDB JSON-like documents me data store karta hai
5. Result backend ko return hota hai

# 🧠 Important Points:
- Schema flexible
- Fast read/write
- Scalable


