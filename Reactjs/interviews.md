# 🟢 BASIC (Freshers / Service Companies)
(TCS, Infosys, Wipro, Accenture, Capgemini)
1. What is React?
2. Why React is faster than traditional JS?
3. What is JSX?
4. Difference between HTML vs JSX
5. What is a component?
6. Functional vs Class components
7. What are props?
8. What is state?
9. Difference between state and props
10. Can we update props?
11. What is Virtual DOM?
12. Real DOM vs Virtual DOM
13. What is SPA (Single Page Application)?
14. What is React Fragment?
15. What is key in React?
16. Why keys are important?
17. What is conditional rendering?
18. How to handle events in React?
19. What is default export vs named export?
20. What is strict mode?

🟡 INTERMEDIATE
⚡ Hooks
1. What are hooks?
2. Why hooks were introduced?
3. Rules of hooks
4. useState working
5. useEffect lifecycle
6. Dependency array in useEffect
7. Cleanup function in useEffect
8. Difference between useEffect & useLayoutEffect
9. What is useRef?
10. Difference between useRef & useState
11. What is useMemo?
12. What is useCallback?
13. useMemo vs useCallback
14. What is custom hook?
15. How to create custom hook?


# 🧠 Rendering & Performance
1. How React re-renders?
2. What causes re-render?
3. How to prevent unnecessary re-renders?
4. What is memoization?
5. What is React.memo?
6. What is lazy loading?
7. What is code splitting?
8. What is Suspense?

# 🔄 Forms & Data
1. controlled vs Uncontrolled components
2. How to handle forms?
3. How to validate forms?
4. What is lifting state up?
5. How parent-child communication works?
6. How to pass data child to parent?

# 🔵 ADVANCED
🏗 Architecture
1. What is reconciliation?
2. What is Fiber architecture?
3. How diffing algorithm works?
4. What is hydration?
5. CSR vs SSR
6. What is Next.js?
7. Why Next.js over React?

# 🧩 Redux / State Management
1. What is Redux?
2. Redux flow
3. What is store?
4. What is reducer?
5. What is action?
6. What is dispatch?
7. Redux vs Context API
8. What is middleware?
9. Redux Thunk
10. Redux Saga
11. What is RTK (Redux Toolkit)?
12. Advantages of RTK

# 🌐 API & Async
1. How to call API in React?
2. Axios vs Fetch
3. Error handling in API
4. How to show loader?
5. How to handle pagination?
6. How to debounce API calls?
7. What is throttling?


# 🔐 Security & Best Practices
1. How to prevent XSS?
2. How to protect routes?
3. Authentication in React
4. Authorization vs Authentication
5. JWT handling in React
6. Environment variables
7. How to store tokens securely?

# 🧪 TESTING
1. what is Jest?
2. What is React Testing Library?
3. Unit vs Integration testing
4. How to test hooks?
5. Snapshot testing
****
# 1️⃣ What is React?
📌 Theory
React is a JavaScript library used to build fast, interactive user interfaces, especially Single Page Applications (SPA).
 - Developed by Facebook
 - Component-based
 - uses Virtual DOM
 - Declarative UI

👉 Instead of updating the whole page, React updates only required parts.

# 💻 Code Example
```
function App() {
  return <h1>Hello React</h1>;
}

export default App;
```
# 2️⃣ Why React is Faster?
📌 Theory
React is fast because of:
- Virtual DOM
- Diffing Algorithm
- Batch updates
- Component reusability

👉 React compares previous Virtual DOM with new Virtual DOM and updates only changed nodes.

# 3️⃣ What is JSX?
📌 Theory
JSX = JavaScript + HTML-like syntax
- JSX is not HTML
- It gets converted into React.createElement()
# 💻 JSX Code
```
const element = <h1>Hello JSX</h1>;
```
# 👇 Without JSX
```
const element = React.createElement("h1", null, "Hello JSX");
```
# 4️⃣ Difference Between HTML and JSX
```
| HTML                   | JSX                  |
| ---------------------- | -------------------- |
| class                  | className            |
| for                    | htmlFor              |
| attributes are strings | attributes can be JS |
| cannot use JS directly | can use JS with `{}` |
```
# 💻 Example
```
<h1 className="title">{10 + 20}</h1>
```
# 5️⃣ What is a Component?
📌 Theory
A component is a reusable piece of UI.
Types:
1. Functional Component ✅ (Most used)
2. Class Component ❌ (Old)

# 💻 Functional Component
```
function Welcome() {
  return <h2>Welcome User</h2>;
}
```
# 6️⃣ Functional vs Class Component
```
| Functional | Class             |
| ---------- | ----------------- |
| Simple     | Complex           |
| Hooks used | Lifecycle methods |
| Faster     | Slower            |
| Preferred  | Deprecated        |
```
# 7️⃣ What are Props?
📌 Theory
Props = data passed from parent to child
- Props are read-only
- Cannot be modified inside child

# 💻 Example
```
function Child(props) {
  return <h2>Hello {props.name}</h2>;
}

function Parent() {
  return <Child name="Sonam" />;
}
```
# 8️⃣ What is State?
📌 Theory
State is component’s own data that can change.
- Managed inside component
- When state changes → component re-renders

# 💻 Example (useState)
```
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
    </>
  );
}
```
# 9️⃣ State vs Props
| State    | Props              |
| -------- | ------------------ |
| Mutable  | Immutable          |
| Local    | Passed from parent |
| useState | function arguments |
# 🔟 Can We Update Props?
❌ NO

Props are read-only.

❌ Wrong:
```
props.name = "New";
```
# ✅ Correct:
- Update state in parent
- Pass new props

# 1️⃣1️⃣ What is Virtual DOM?
📌 Theory
Virtual DOM is a lightweight copy of Real DOM.

Flow:
```
State Change → New Virtual DOM → Compare → Update Real DOM
```
# 1️⃣2️⃣ Real DOM vs Virtual DOM
| Real DOM             | Virtual DOM       |
| -------------------- | ----------------- |
| Slow                 | Fast              |
| Re-renders full tree | Updates only diff |
| Browser dependent    | JS object         |

# 1️⃣3️⃣ What is SPA?
📌 Theory
SPA = Single Page Application
- Loads one HTML page
- Page doesn’t reload
- Content updates dynamically

Examples:
- Gmail
- Facebook
- Instagram

# 1️⃣4️⃣ What is React Fragment?
📌 Theory
Used to return multiple elements without extra div

# 💻 Example
```
<>
  <h1>Hello</h1>
  <p>World</p>
</>
```
# 1️⃣5️⃣ What is Key in React?
📌 Theory
Key helps React identify which item changed in lists.

💻 Example
```
{items.map(item => (
  <li key={item.id}>{item.name}</li>
))}
```
❌ Using index as key (bad for performance)

# 1️⃣6️⃣ Conditional Rendering
💻 Example
```
{isLoggedIn ? <Dashboard /> : <Login />}
```
# 1️⃣7️⃣ Handling Events
💻 Example
```
<button onClick={handleClick}>Click</button>

function handleClick() {
  alert("Clicked");
}
```
# 1️⃣8️⃣ Default vs Named Export
💻 Default
```
export default App;
import App from "./App";
```
# 💻 Named
```
export const App = () => {};
import { App } from "./App";
```
# 1️⃣9️⃣ What is Strict Mode?
📌 Theory
 Used to find:
- Unsafe lifecycle
- Deprecated APIs
- Side effects

💻 Example
```
<React.StrictMode>
  <App />
</React.StrictMode>
```
********
# 2️⃣1️⃣ What are Hooks?
📌 Theory
Hooks are special functions that let you use state and lifecycle features in functional components.

👉 Before hooks → only class components had state
👉 After hooks → functional components do everything
Common Hooks:
- useState
- useEffect
- useRef
- useMemo
- useCallback
- useContext

# 2️⃣2️⃣ Why Hooks Were Introduced?
📌 Problems with Class Components

❌  Too much boilerplate
❌  this confusion
❌  Hard to reuse logic
❌  Lifecycle methods are complex

# ✅ Hooks Advantages

✔  Clean code
✔  No this
✔  Logic reuse via custom hooks
✔  Easier testing 

 # 2️⃣3️⃣ Rules of Hooks ❗ (Very Important)
📌 Rules
1. Call hooks only at top level
2. Call hooks only inside React function components
3. Do NOT call hooks inside loops, conditions, or nested functions

❌ Wrong:
```
if (x > 0) {
  useState(0);
}
```
✅ Correct:'
```
const [count, setCount] = useState(0);
```
# 2️⃣4️⃣ useState Hook
📌 Theory
useState is used to create and update state.

Syntax:
```
const [state, setState] = useState(initialValue);
```
# 💻 Counter Example
```
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <h2>{count}</h2>
      <button onClick={() => setCount(count + 1)}>+</button>
      <button onClick={() => setCount(count - 1)}>-</button>
    </>
  );
}
```
👉 State change → component re-renders

# 2️⃣5️⃣ useEffect Hook (🔥 MOST IMPORTANT)
📌 Theory
useEffect is used for side effects:
- API calls
- DOM manipulation
- Timers
- Subscriptions

It replaces:
- componentDidMount
- componentDidUpdate
- componentWillUnmount

📌 Syntax

```
useEffect(() => {
  // side effect
}, [dependency]);
```
# 2️⃣6️⃣ useEffect with Different Cases
✅ 1. Runs on Every Render
```
useEffect(() => {
  console.log("Rendered");
});
```
 ✅ 2. Runs Only Once (componentDidMount)
 ```
useEffect(() => {
  console.log("Mounted");
}, []);
```
✅ 3. Runs When Dependency Changes
```
useEffect(() => {
  console.log("Count changed");
}, [count]);
```
# 2️⃣7️⃣ Cleanup Function in useEffect
📌 Theory
Cleanup runs when:
- Component unmounts
- Dependency changes

Used for:
- Clearing timers
- Removing event listeners

💻 Example
```
useEffect(() => {
  const timer = setInterval(() => {
    console.log("Running...");
  }, 1000);

  return () => {
    clearInterval(timer);
  };
}, []);
```

# 2️⃣8️⃣ useEffect vs useLayoutEffect
| useEffect        | useLayoutEffect   |
| ---------------- | ----------------- |
| Async            | Sync              |
| Runs after paint | Runs before paint |
| Non-blocking     | Blocking          |
| Preferred        | Rare cases        |

# 💻 useLayoutEffect Example
```
useLayoutEffect(() => {
  console.log("DOM measured");
}, []);
```
# 2️⃣9️⃣ useRef Hook
📌 Theory
useRef is used to:
1. Access DOM directly
2. Store mutable value without re-render

💻 DOM Access Example
```
import { useRef } from "react";

function InputFocus() {
  const inputRef = useRef();

  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>
        Focus
      </button>
    </>
  );
}
```
# 💡 Difference: useRef vs useState
| useRef       | useState         |
| ------------ | ---------------- |
| No re-render | Causes re-render |
| Mutable      | Immutable        |
| Used for DOM | Used for UI      |

# 3️⃣0️⃣ useMemo Hook
📌 Theory
useMemo is used to memoize expensive calculations.

👉 Prevents recalculating value on every render.

💻 Example
```
import { useMemo } from "react";

function ExpensiveCalc({ num }) {
  const result = useMemo(() => {
    console.log("Calculating...");
    return num * 100;
  }, [num]);

  return <h2>{result}</h2>;
}
```
# 3️⃣1️⃣ useCallback Hook
📌 Theory
useCallback memoizes functions.

👉 Used when passing functions to child components.

💻 Example
```
const handleClick = useCallback(() => {
  console.log("Clicked");
}, []);
```
# 3️⃣2️⃣ useMemo vs useCallback
| useMemo        | useCallback       |
| -------------- | ----------------- |
| Memoizes value | Memoizes function |
| Returns value  | Returns function  |
| Performance    | Performance       |


# 3️⃣3️⃣ React.memo
📌 Theory
React.memo prevents unnecessary re-render of child component.

💻 Example
```
const Child = React.memo(({ value }) => {
  console.log("Child Rendered");
  return <p>{value}</p>;
});
```
# 3️⃣4️⃣ Custom Hooks
📌 Theory
Custom hook = reusable logic
Rules:
- Name starts with use
- Can use other hooks

💻 Example: useCounter Hook
```
import { useState } from "react";

function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);

  return { count, increment, decrement };
}
```
# 💻 Usage
```
const { count, increment, decrement } = useCounter();
```
# 3️⃣5️⃣ Why Custom Hooks?

✔  Code reuse
✔  Clean components
✔  Better separation of logic

# 3️⃣6️⃣ How Does React Render a Component?
📌 Theory
React rendering means:
1. Component function is called
2. JSX is converted to Virtual DOM
3. React compares old vs new Virtual DOM
4. Only changed nodes update in Real DOM

🔁 Rendering ≠ DOM update
👉 Rendering happens often, DOM updates are optimized

💻 Example
```
function App() {
  console.log("Rendered");
  return <h1>Hello</h1>;
}
```

👉 Every state/prop change → function runs again

# 3️⃣7️⃣ What Causes Re-Render?
📌 Main Reasons
1. State change
2. Props change
3. Parent re-renders
4. Context change
5. Key change

💻 Example
```
setCount(count + 1); // triggers re-render
```

# 3️⃣8️⃣ Why Parent Re-Render Causes Child Re-Render?
📌 Theory
By default:
- When parent renders
- All children render again

Even if props didn’t change ❌

💻 Example
```
function Parent() {
  const [count, setCount] = useState(0);

  return (
    <>
      <button onClick={() => setCount(count + 1)}>+</button>
      <Child />
    </>
  );
}
```

👉 Child re-renders unnecessarily

# 3️⃣9️⃣ How to Prevent Unnecessary Re-Render?
✅ Solutions
1. React.memo
2. useMemo
3. useCallback
4. Proper key
5. Avoid inline functions
6. Split components

# 4️⃣0️⃣ React.memo
📌 Theory
Prevents child re-render if props don’t change.

💻 Example
```
const Child = React.memo(() => {
  console.log("Child rendered");
  return <p>Child</p>;
});
```

# 4️⃣1️⃣ Inline Functions Problem ❗
📌 Theory

Inline functions create new reference on every render.

❌ Bad
```
<Child onClick={() => console.log("Hi")} />
```

✅ Good
```
const handleClick = useCallback(() => {
  console.log("Hi");
}, []);

<Child onClick={handleClick} />
```

# 4️⃣2️⃣ useCallback for Performance
📌 Theory
useCallback memoizes function reference.

💻 Example
```
const increment = useCallback(() => {
  setCount(c => c + 1);
}, []);
```

# 4️⃣3️⃣ useMemo for Performance
📌 Theory
Avoids expensive recalculations.

💻 Example
```
const result = useMemo(() => heavyCalc(num), [num]);
```
# 4️⃣4️⃣ What is Memoization?
📌 Theory
Memoization = store result & reuse when inputs same.

Used by:
- useMemo
- useCallback
- React.memo

# 4️⃣5️⃣ What is Reconciliation?
📌 Theory
Reconciliation is process of:
- Comparing old Virtual DOM with new Virtual DOM

Uses Diffing Algorithm.

# 4️⃣6️⃣ Diffing Algorithm Rules
1. Different element → destroy old, create new
2. Same element → update attributes
3. Keys help identify list items

💻 List Example
```
items.map(item => (
  <li key={item.id}>{item.name}</li>
));
```
# 4️⃣7️⃣ What is Fiber Architecture?
📌 Theory
Fiber is React’s new reconciliation engine.

Benefits:
✔ Incremental rendering
✔ Pausing & resuming work
✔ Better responsiveness

# 4️⃣8️⃣ What is Lazy Loading?
📌 Theory
Load component only when needed.

💻 React.lazy Example
```
const Dashboard = React.lazy(() => import("./Dashboard"));
```
# 4️⃣9️⃣ What is Suspense?
📌 Theory
Used to show fallback UI while lazy component loads.

💻 Example
```
<Suspense fallback={<h2>Loading...</h2>}>
  <Dashboard />
</Suspense>
```

# 5️⃣0️⃣ What is Code Splitting?
📌 Theory

Split JS bundle into smaller chunks.

Benefits:
✔ Faster initial load
✔ Better performance

# 5️⃣1️⃣ What is Key Prop & Performance?
📌 Theory
Wrong keys → wrong DOM updates → bugs & slowness

❌ Bad
```
key={index}
```

✅ Good
```
key={item.id}
```
# 5️⃣2️⃣ When NOT to Optimize?
📌 Rule

“Premature optimization is the root of all evil”
Optimize only when:
- Performance issue exists
- Large lists
- Heavy calculations

# 5️⃣3️⃣ Real Interview Question ⭐

Q: Why component renders but DOM doesn’t update?
Answer:
- Render creates Virtual DOM
- Diffing finds no change
- No Real DOM update

# 5️⃣4️⃣ Another Interview Question ⭐

Q: Why useCallback + React.memo together?

Answer:
- React.memo checks props
- Inline functions create new reference
- useCallback stabilizes function reference

# 5️⃣5️⃣ Performance Checklist (Tell Interviewer)

✔ Avoid inline functions
✔ Use React.memo
✔ Use useCallback & useMemo
✔ Lazy loading
✔ Proper keys
✔ Split components


# 5️⃣7️⃣ What is Redux?
📌 Theory
Redux is a state management library used to manage global state in React apps.

👉 Used when:
- Many components need same data
- Prop drilling becomes messy
- App is large & complex
- Redux follows single source of truth.

# 🧠 Example Problem

❌ Passing props:
App → Header → Dashboard → Profile

✅ Redux:
Any component can directly access data.

# 5️⃣8️⃣ Redux Core Principles

1️⃣ Single Store
2️⃣ State is Read-Only
3️⃣ Changes via Pure Functions (Reducers)

# 5️⃣9️⃣ Redux Flow (🔥 INTERVIEW FAVORITE)
- UI → dispatch(action)
- action → reducer
- reducer → store update
- store → UI update

# 6️⃣0️⃣ What is Store?
📌 Theory
Store:
- Holds entire app state
- Created using createStore (old) or configureStore (RTK)

# 6️⃣1️⃣ What is an Action?
📌 Theory
Action is a plain JS object describing what happened.

💻 Example
```
{
  type: "INCREMENT"
}
```
# 6️⃣2️⃣ What is a Reducer?
📌 Theory
- Reducer is a pure function that:
- Takes old state + action
- Returns new state

💻 Example
```
function counterReducer(state = 0, action) {
  switch (action.type) {
    case "INCREMENT":
      return state + 1;
    default:
      return state;
  }
}
```
# 6️⃣3️⃣ What is Dispatch?
📌 Theory
Dispatch sends action to reducer.

💻 Example
```
dispatch({ type: "INCREMENT" });
```
# 6️⃣4️⃣ Problems with Classic Redux ❌

❌ Too much boilerplate
❌ Separate files for actions, reducers
❌ Complex setup

👉 Solution = Redux Toolkit (RTK) ✅

🔥 REDUX TOOLKIT (RTK)
# 6️⃣5️⃣ What is Redux Toolkit?
📌 Theory
RTK is the official, recommended way to use Redux.

Benefits:
- ✔ Less code
- ✔ Built-in best practices
- ✔ Easier async handling

# 6️⃣6️⃣ RTK Key Concepts
- configureStore
- createSlice
- createAsyncThunk

# 6️⃣7️⃣ createSlice (MOST IMPORTANT)
📌 Theory
- createSlice automatically:
- Creates actions
- Creates reducer

💻 Counter Slice Example
```
import { createSlice } from "@reduxjs/toolkit";

const counterSlice = createSlice({
  name: "counter",
  initialState: { value: 0 },
  reducers: {
    increment: (state) => {
      state.value += 1; // immer allows mutation
    },
    decrement: (state) => {
      state.value -= 1;
    }
  }
});

export const { increment, decrement } = counterSlice.actions;
export default counterSlice.reducer;
```
# 6️⃣8️⃣ configureStore
💻 Store Setup
```
import { configureStore } from "@reduxjs/toolkit";
import counterReducer from "./counterSlice";

export const store = configureStore({
  reducer: {
    counter: counterReducer
  }
});
```
# 6️⃣9️⃣ Provider (Connecting React & Redux)
💻 index.js
```
import { Provider } from "react-redux";
import { store } from "./store";

<Provider store={store}>
  <App />
</Provider>
```
# 7️⃣0️⃣ useSelector & useDispatch
📌 Theory
- useSelector → read data
- useDispatch → send action

💻 Component Example
```
import { useSelector, useDispatch } from "react-redux";
import { increment, decrement } from "./counterSlice";

function Counter() {
  const count = useSelector(state => state.counter.value);
  const dispatch = useDispatch();

  return (
    <>
      <h2>{count}</h2>
      <button onClick={() => dispatch(increment())}>+</button>
      <button onClick={() => dispatch(decrement())}>-</button>
    </>
  );
}
```
# 7️⃣1️⃣ Why Reducer Code Looks Mutable?
📌 Theory

RTK uses Immer internally.

👉 It converts mutable code into immutable updates safely.

# 7️⃣2️⃣ Redux vs Context API (🔥 ASKED A LOT)
| Redux               | Context    |
| ------------------- | ---------- |
| External library    | Built-in   |
| Best for large apps | Small apps |
| Middleware support  | No         |
| Debugging tools     | Limited    |

# 7️⃣3️⃣ What is Middleware?
📌 Theory
Middleware sits between:
```
dispatch → reducer
```

Used for:
- Logging
- API calls
- Async tasks

# 7️⃣4️⃣ Redux Thunk
📌 Theory

Thunk allows async logic in Redux.

💻 Thunk Example
```
export const fetchUsers = () => async (dispatch) => {
  const res = await fetch("/users");
  const data = await res.json();
  dispatch(setUsers(data));
};
```
# 7️⃣5️⃣ createAsyncThunk (RTK Way 🔥)
💻 API Example
```
import { createAsyncThunk } from "@reduxjs/toolkit";

export const fetchUsers = createAsyncThunk(
  "users/fetch",
  async () => {
    const res = await fetch("https://api.example.com/users");
    return res.json();
  }
);
```
💻 Handling States
```
extraReducers: (builder) => {
  builder
    .addCase(fetchUsers.pending, (state) => {
      state.loading = true;
    })
    .addCase(fetchUsers.fulfilled, (state, action) => {
      state.loading = false;
      state.users = action.payload;
    })
    .addCase(fetchUsers.rejected, (state) => {
      state.loading = false;
      state.error = true;
    });
}
```
7️⃣6️⃣ Redux Toolkit Advantages (Say This!)

- ✔ Less boilerplate
- ✔ Built-in async support
- ✔ Easy to scale
- ✔ Official recommendation

# 7️⃣7️⃣ Common Interview Questions ⭐
- ❓ Why Redux if React has state?
👉 React state is local, Redux is global

- ❓ Can Redux replace React state?
👉 NO. Use Redux only when needed.

- ❓ When NOT to use Redux?
👉 Small apps, few components, simple state


# 7️⃣8️⃣ How to Call API in React?
📌 Theory
API calls are side effects, so we use:
👉 useEffect
Steps:
1. Call API
2. Store response in state
3. Render UI

💻 Using Fetch
```
import { useEffect, useState } from "react";

function Users() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then(res => res.json())
      .then(data => setUsers(data));
  }, []);

  return (
    <ul>
      {users.map(u => <li key={u.id}>{u.name}</li>)}
    </ul>
  );
}
```
# 7️⃣9️⃣ Axios vs Fetch (🔥 Interview Question)
| Fetch             | Axios            |
| ----------------- | ---------------- |
| Built-in          | External library |
| Manual JSON parse | Auto JSON        |
| No interceptors   | Has interceptors |
| More boilerplate  | Cleaner          |

💻 Axios Example
```
import axios from "axios";

useEffect(() => {
  axios.get("/users")
    .then(res => setUsers(res.data));
}, []);
```
# 8️⃣0️⃣ Error Handling in API Calls
📌 Theory
Always handle:
- Loading
- Error
- Success

💻 Example
```
const [loading, setLoading] = useState(true);
const [error, setError] = useState(null);

useEffect(() => {
  fetch("/users")
    .then(res => res.json())
    .then(data => setUsers(data))
    .catch(err => setError(err))
    .finally(() => setLoading(false));
}, []);
```
# 8️⃣1️⃣ Show Loader While Fetching
```
{loading && <h3>Loading...</h3>}
{error && <h3>Error occurred</h3>}
```
# 8️⃣2️⃣ Controlled vs Uncontrolled Components
📌 Controlled Component

Form data controlled by state.
```
const [name, setName] = useState("");

<input
  value={name}
  onChange={e => setName(e.target.value)}
/>
```
📌 Uncontrolled Component
Uses ref.
```
const inputRef = useRef();

<input ref={inputRef} />
```

✅ Controlled preferred for validation.

# 8️⃣3️⃣ Form Handling in React
💻 Basic Form
```
function Login() {
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");

  const submit = (e) => {
    e.preventDefault();
    console.log(email, password);
  };

  return (
    <form onSubmit={submit}>
      <input onChange={e => setEmail(e.target.value)} />
      <input type="password" onChange={e => setPassword(e.target.value)} />
      <button>Login</button>
    </form>
  );
}
```
# 8️⃣4️⃣ Form Validation (Manual)
```
if (!email.includes("@")) {
  alert("Invalid email");
}

```
👉 In real projects:
- Formik
- React Hook Form
- Yup

# 8️⃣5️⃣ What is Authentication?
📌 Theory
Authentication = Who are you?

Example:
- Login
- Signup

Uses:
- JWT
- Sessions
- OAuth

# 8️⃣6️⃣ JWT Authentication Flow (🔥 Very Important)
- User logs in
- Server returns JWT
- Store token
- Send token with API
- Server verifies token


# 8️⃣7️⃣ Where to Store JWT? ❗
| Location         | Safe?           |
| ---------------- | --------------- |
| LocalStorage     | ❌ XSS risk      |
| SessionStorage   | ❌               |
| HTTP-only Cookie | ✅ Best          |
| Memory           | ✅ (short-lived) |


👉 Interview Answer:

HTTP-only cookies are safest

# 8️⃣8️⃣ Protected Routes in React
💻 Example
```
import { Navigate } from "react-router-dom";

function PrivateRoute({ children }) {
  const isAuth = localStorage.getItem("token");
  return isAuth ? children : <Navigate to="/login" />;
}
```
💻 Usage
```
<Route
  path="/dashboard"
  element={
    <PrivateRoute>
      <Dashboard />
    </PrivateRoute>
  }
/>
```
# 8️⃣9️⃣ Authorization vs Authentication
| Authentication | Authorization       |
| -------------- | ------------------- |
| Who are you    | What can you access |
| Login          | Roles               |
| JWT            | Permissions         |

# 9️⃣0️⃣ How to Prevent XSS?
📌 Theory

XSS = Injecting malicious JS.

✅ Prevention

✔ Don’t use dangerouslySetInnerHTML
✔ Escape user input
✔ Use HTTP-only cookies

# 9️⃣1️⃣ Environment Variables
📌 Theory
Used to store:
- API URLs
- Keys

💻 Example
```
REACT_APP_API_URL=https://api.example.com
```
```
process.env.REACT_APP_API_URL
```
# 9️⃣2️⃣ Logout Implementation
```
localStorage.removeItem("token");
navigate("/login");
```
# 9️⃣3️⃣ Interview Question ⭐

Q: Why use useEffect for API calls?
A: Because API calls are side effects and should run after render.

# 9️⃣4️⃣ Interview Question ⭐

Q: How to cancel API call on unmount?
```
const controller = new AbortController();

fetch(url, { signal: controller.signal });

return () => controller.abort();
```
9️⃣5️⃣ Best Practices (Say This!)

✔ Always handle loading & error
✔ Use axios interceptors
✔ Secure tokens
✔ Use env variables
✔ Protect routes
