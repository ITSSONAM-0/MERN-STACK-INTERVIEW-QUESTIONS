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
