# 🔹 What is React?
- React is a JavaScript library used to build fast, interactive user interfaces (UI), mainly for single-page applications (SPA).

# 🔹 Why React?
- Component-based 🧩
- Reusable code
- Fast (Virtual DOM)
- Easy to manage UI state

# 🔹 React vs JavaScript
```
| JavaScript              | React           |
| ----------------------- | --------------- |
| Manual DOM manipulation | Virtual DOM     |
| Hard to manage UI       | Easy UI updates |
| No structure            | Component-based |
```
# 🔹 Install React
```
npx create-react-app myapp
cd myapp
npm start
```

# 🔹 Folder Structure
```
src/
 ├── App.js
 ├── index.js
 ├── components/
```
# 🔹 index.js (Entry Point)
```
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```
# 🔹 App.js (Main Component)
```
function App() {
  return <h1>Hello React</h1>;
}

export default App;
```
# 🔹 What is JSX?
- JSX = JavaScript + HTML
```
const element = <h1>Hello World</h1>;
```
- ✔️ JSX makes code readable
- ❌ Browser does not understand JSX → Babel converts it

  # 🔹 JSX Rules
- Must return one parent element
- Use className instead of class
- Use {} for JS
```
const name = "Sonam";
return <h1>Hello {name}</h1>;
```
# 🔹 Components
- Components are reusable UI blocks

#🔹 Functional Component
```
function Welcome() {
  return <h2>Welcome to React</h2>;
}
```
# 🔹 Using Component
```
function App() {
  return <Welcome />;
}
```
# 🔹 What are Props?
- Props are data passed from parent to child component
✔️ Read-only
✔️ Used for reusability

# 🔹 Example
```
function Student(props) {
  return <h2>Name: {props.name}</h2>;
}
```
# 🔹 Passing Props
```
function App() {
  return <Student name="Sonam" />;
}
```
# 🔹 Props with Multiple Values
```
function Student({ name, age }) {
  return (
    <p>
      {name} is {age} years old
    </p>
  );
}
```
# 🔹 Why Props?
- Dynamic UI
- Component reuse
- Parent → Child communication

# 🔹 What is State?
- State is data that can change inside a component.

Props ❌ change
State ✔️ change

# 🔹 useState Hook
```
import { useState } from "react";
```
# 🔹 Counter Example
```
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <h2>{count}</h2>
      <button onClick={() => setCount(count + 1)}>+</button>
    </>
  );
}
```
# 🔹 Important Rules
- Never modify state directly
- Always use setter function

❌ count = count + 1
✔️ setCount(count + 1)
# 🔹 Mini App: Greeting App
```
import { useState } from "react";

function App() {
  const [name, setName] = useState("");

  return (
    <>
      <input 
        type="text" 
        onChange={(e) => setName(e.target.value)} 
      />
      <h2>Hello {name}</h2>
    </>
  );
}

export default App;
```
# 🔹 What are Hooks?
- Hooks let you use state and lifecycle features in functional components.

# 🔹 useEffect
- Used for:
- API calls
- Side effects
- Component lifecycle

# 🔹 Syntax
```
useEffect(() => {
  // code
}, []);
```
# 🔹 Example: Page Load
```
import { useEffect } from "react";

function App() {
  useEffect(() => {
    console.log("Component Mounted");
  }, []);

  return <h1>Hello</h1>;
}
```
# 🔹 Dependency Array
```
| Dependency | Meaning             |
| ---------- | ------------------- |
| `[]`       | Run once            |
| `[state]`  | Run on state change |
| no array   | Run every render    |
```
# 🔹 Show UI Based on Condition
```
function App() {
  const isLoggedIn = true;

  return (
    <h1>{isLoggedIn ? "Welcome" : "Please Login"}</h1>
  );
}
```
# 🔹 Using && Operator
```
{isLoggedIn && <h1>Dashboard</h1>}
```
# 🔹 Rendering Lists
```
const names = ["Sonam", "Riya", "Aman"];

function App() {
  return (
    <>
      {names.map((name) => (
        <h2>{name}</h2>
      ))}
    </>
  );
}
```
# 🔹 Keys (Very Important)
- Keys help React identify elements.
```
{names.map((name, index) => (
  <h2 key={index}>{name}</h2>
))}
```
# 🔥 Interview Tips
- Props → Parent to Child
- State → Component memory
- useEffect → Side effects
- Keys → Performance

# 🔹 What is an API?
- API = Application Programming Interface

- 👉 It allows frontend (React) to talk to backend/server
- 👉 Example:
      - Get users
      - Login
      - Products list

# 🔹 Why Axios (instead of fetch)?
```
| Axios                 | Fetch          |
| --------------------- | -------------- |
| Easy syntax           | Little complex |
| Auto JSON             | Manual JSON    |
| Better error handling | Less           |
| Interceptors          | ❌              |
```
✔️ Industry uses Axios more

# 🔹 Install Axios
```
npm install axios
```
# 🔹 Basic Axios GET Request
📌 Step 1: Import Axios
```
import axios from "axios";
```
📌 Step 2: API Call using useEffect
```
import { useEffect, useState } from "react";
import axios from "axios";

function App() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((response) => {
        setUsers(response.data);
      })
      .catch((error) => {
        console.log(error);
      });
  }, []);

  return (
    <>
      <h1>User List</h1>
      {users.map((user) => (
        <p key={user.id}>{user.name}</p>
      ))}
    </>
  );
}

export default App;
```
# 🔹 Explanation (VERY IMPORTANT)
- useEffect → call API on page load
- response.data → actual data
- setUsers → store data in state
- map() → display list
# 🔹 Axios POST Request (Form Data)
```
axios.post("https://jsonplaceholder.typicode.com/posts", {
  title: "React",
  body: "Axios API",
  userId: 1,
});
```
# 🔹 Example: Add User Form
```
function App() {
  const [name, setName] = useState("");

  const addUser = () => {
    axios.post("https://jsonplaceholder.typicode.com/users", {
      name: name,
    });
  };

  return (
    <>
      <input onChange={(e) => setName(e.target.value)} />
      <button onClick={addUser}>Add</button>
    </>
  );
}
```
# 🔹 Loading & Error Handling (Interview Favorite ⭐)
```
const [loading, setLoading] = useState(true);
const [error, setError] = useState("");

useEffect(() => {
  axios
    .get("https://jsonplaceholder.typicode.com/users")
    .then((res) => {
      setUsers(res.data);
      setLoading(false);
    })
    .catch(() => {
      setError("Something went wrong");
      setLoading(false);
    });
}, []);
```
```
if (loading) return <h2>Loading...</h2>;
if (error) return <h2>{error}</h2>;
```
# 🔹 Axios vs useEffect (Interview Line)
- 👉 API calls should be inside useEffect to avoid infinite loop

# ❓ Q1. What is React?
- ✅ React is a JavaScript library for building component-based user interfaces.

# ❓ Q2. What is JSX?

✅ JSX is a syntax extension that allows writing HTML inside JavaScript.

# ❓ Q3. Difference between Props and State?
```
| Props              | State                    |
| ------------------ | ------------------------ |
| Passed from parent | Managed inside component |
| Read-only          | Can change               |
| Used for data      | Used for UI updates      |
```
# ❓ Q4. What are Hooks?

✅ Hooks are functions that allow using state and lifecycle features in functional components.

Example:
```
useState()
useEffect()
```
# ❓ Q5. Why use useEffect?
- ✅ To handle side effects:
- API calls
- Timers
- Subscriptions

# ❓ Q6. What is Virtual DOM?
- ✅ Virtual DOM is a lightweight copy of real DOM that improves performance by updating only changed elements.

# ❓ Q7. Why keys are important?
- ✅ Keys help React identify elements and improve performance during re-rendering.

# ❓ Q8. Controlled vs Uncontrolled Components?
- Controlled → State controls input
- Uncontrolled → DOM controls input

  # ❓ Q9. What is lifting state up?
 - ✅ Sharing state between components by moving it to common parent.

# ❓ Q10. How to prevent re-render?
- useMemo
- useCallback
- React.memo

 # nterview Tip (Very Important)

Always say:

- “React follows unidirectional data flow and component reusability”

  # 1️⃣ useMemo
🔹 What is useMemo?
- useMemo memorizes the result of a calculation so it doesn’t run again on every re-render.
- 👉 Used for expensive calculations

# 🔹 Problem Without useMemo
```
function App() {
  const [count, setCount] = useState(0);

  const expensiveCalculation = () => {
    console.log("Calculating...");
    return count * 1000;
  };

  return (
    <>
      <h2>{expensiveCalculation()}</h2>
      <button onClick={() => setCount(count + 1)}>+</button>
    </>
  );
}
```
- ❌ Runs every render
- ❌ Performance issue

  # ✅ Solution using useMemo
 ```
  import { useMemo, useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  const result = useMemo(() => {
    console.log("Calculating...");
    return count * 1000;
  }, [count]);

  return (
    <>
      <h2>{result}</h2>
      <button onClick={() => setCount(count + 1)}>+</button>
    </>
  );
}
```
# 🔹 Interview Line
- “useMemo is used to optimize performance by memoizing expensive calculations.”

# 2️⃣ useCallback
## 🔹 What is useCallback?
- useCallback memorizes a function, not a value.
- 👉 Used when passing functions to child components

# 🔹 Problem Without useCallback
```
function Parent() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    console.log("Clicked");
  };

  return <Child onClick={handleClick} />;
}
```
- ❌ Function recreated on every render
- ❌ Child re-renders unnecessarily

  # ✅ Solution using useCallback
 ```
  import { useCallback } from "react";

const handleClick = useCallback(() => {
  console.log("Clicked");
}, []);
```
# 🔹 Full Example with React.memo
```
const Child = React.memo(({ onClick }) => {
  console.log("Child rendered");
  return <button onClick={onClick}>Click</button>;
});

function Parent() {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    console.log("Clicked");
  }, []);

  return (
    <>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>+</button>
      <Child onClick={handleClick} />
    </>
  );
}
```
# 🔹 Interview Line
- “useCallback prevents unnecessary re-renders by memoizing function references.”

- 🔥 useMemo vs useCallback (VERY IMPORTANT)
```
| useMemo               | useCallback            |
| --------------------- | ---------------------- |
| Memoizes value        | Memoizes function      |
| For heavy calculation | For function reference |
| Returns value         | Returns function       |
```
- 👉 useCallback = useMemo for functions

# 🔷 REACT INTERVIEW CODING ROUND QUESTIONS
# 1️⃣ Counter App
```
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>+</button>
      <button onClick={() => setCount(count - 1)}>-</button>
    </>
  );
}
```
# 2️⃣ Todo List (Most Asked 🔥)
```
function Todo() {
  const [task, setTask] = useState("");
  const [todos, setTodos] = useState([]);

  const addTodo = () => {
    setTodos([...todos, task]);
    setTask("");
  };

  return (
    <>
      <input value={task} onChange={(e) => setTask(e.target.value)} />
      <button onClick={addTodo}>Add</button>

      {todos.map((t, i) => (
        <p key={i}>{t}</p>
      ))}
    </>
  );
}
```
# 3️⃣ Search Filter
```
function Search() {
  const [text, setText] = useState("");
  const items = ["React", "Angular", "Vue"];

  const filtered = items.filter((item) =>
    item.toLowerCase().includes(text.toLowerCase())
  );

  return (
    <>
      <input onChange={(e) => setText(e.target.value)} />
      {filtered.map((item, i) => (
        <p key={i}>{item}</p>
      ))}
    </>
  );
}
```
# 4️⃣ Fetch API Data (Coding Round Favorite ⭐)
```
function Users() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((res) => res.json())
      .then((data) => setUsers(data));
  }, []);

  return (
    <>
      {users.map((user) => (
        <p key={user.id}>{user.name}</p>
      ))}
    </>
  );
}
```
# 5️⃣ Show / Hide Password
```
function Password() {
  const [show, setShow] = useState(false);

  return (
    <>
      <input type={show ? "text" : "password"} />
      <button onClick={() => setShow(!show)}>
        {show ? "Hide" : "Show"}
      </button>
    </>
  );
}
```
# Say these confidently:
- “React uses virtual DOM for performance optimization.”
- “useMemo and useCallback are used to avoid unnecessary re-renders.”
- “State updates are asynchronous in React.”
- “Keys help React efficiently update the DOM.”

