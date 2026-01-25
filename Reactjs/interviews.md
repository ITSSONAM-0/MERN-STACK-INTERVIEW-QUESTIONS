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
