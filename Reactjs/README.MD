# Q1. What is React?

React is an open-source JavaScript library used for building fast and interactive user interfaces, mainly for single-page applications. It was developed by Facebook. React follows a component-based architecture, where the UI is divided into small reusable components. Each component manages its own state, which makes the application easier to debug and maintain. React uses a Virtual DOM instead of directly updating the real DOM, which improves performance. When data changes, React updates only the required part of the UI instead of reloading the whole page. This makes applications faster and more efficient. React is widely used because it is flexible, scalable, and works well with other libraries and frameworks.

# Q2. Why is React fast?
React is fast because it uses a Virtual DOM. Instead of updating the real DOM every time data changes, React first updates the Virtual DOM, which is a lightweight copy of the real DOM. React then compares the previous Virtual DOM with the updated one using a process called reconciliation. Only the changed elements are updated in the real DOM. This minimizes expensive DOM operations and improves performance. React also supports component reusability, which reduces redundant code. Features like memoization, lazy loading, and hooks such as useMemo and useCallback further optimize performance. Because of these reasons, React applications feel smooth and responsive.

# Q3. What is JSX?
JSX stands for JavaScript XML. It is a syntax extension used in React that allows developers to write HTML-like code inside JavaScript. JSX makes code more readable and easier to understand. Although it looks like HTML, it is actually converted into JavaScript function calls by Babel. JSX helps in writing UI logic and structure in one place, which improves maintainability. It also prevents injection attacks by escaping values before rendering them. Using JSX is not mandatory in React, but it is highly recommended because it improves developer productivity and makes the code cleaner and more intuitive.

# Q4. Difference between React and Angular
React is a library, while Angular is a full-fledged framework. React focuses mainly on the UI layer, whereas Angular provides complete solutions including routing, state management, and form handling. React uses JavaScript and JSX, while Angular uses TypeScript. React follows a unidirectional data flow, which makes debugging easier. Angular uses two-way data binding, which can be complex for large applications. React is more flexible and lightweight, allowing developers to choose their own libraries. Angular is opinionated and follows a strict structure. React is generally preferred for high-performance and scalable applications.

# Q5. What is Virtual DOM?
The Virtual DOM is a lightweight JavaScript representation of the real DOM. React uses it to improve performance. When the state of a component changes, React updates the Virtual DOM instead of directly modifying the real DOM. Then React compares the updated Virtual DOM with the previous version and identifies the differences. This process is called diffing. Only the changed elements are updated in the real DOM. This reduces unnecessary DOM operations, which are expensive and slow. As a result, applications become faster and more efficient. The Virtual DOM is one of the core reasons why React performs well.

# Q6. Functional vs Class Components
Functional components are simple JavaScript functions that return JSX, while class components are ES6 classes that extend React.Component. Earlier, class components were used for state and lifecycle methods, but with the introduction of hooks, functional components can now handle state and side effects. Functional components are easier to read, write, and test. They have less boilerplate code compared to class components. Class components use lifecycle methods like componentDidMount, while functional components use hooks like useEffect. Today, functional components are preferred because they are cleaner, faster, and more modern.

# Q7. What are props?
Props stand for properties. They are used to pass data from a parent component to a child component. Props are read-only, which means a child component cannot modify them. They help make components reusable and dynamic. For example, the same button component can display different text using props. Props improve code modularity and separation of concerns. In React, props are passed as attributes to components. Using props correctly ensures predictable behavior and better application structure.

# Q8. Can we modify props? Why?
No, props cannot be modified. Props are immutable because they are controlled by the parent component. Allowing child components to change props would break the unidirectional data flow of React. This could make the application unpredictable and hard to debug. If a component needs to change data, it should use state instead. The parent component can pass a function as a prop to allow controlled updates. This design ensures better data consistency and maintainability.

# Q9. What is prop drilling?
Prop drilling occurs when data is passed from a top-level component to deeply nested child components through multiple intermediate components. Even if intermediate components do not need the data, they still have to pass it down. This makes code messy and hard to maintain. Prop drilling can be avoided using React Context API, Redux, or other state management libraries. These tools allow components to access data directly without passing props at every level.

# Q10. How to avoid prop drilling?
Prop drilling can be avoided using Context API, Redux, Zustand, or other global state management solutions. Context API allows you to create a global store and provide data to components directly. Redux centralizes application state in a single store. These approaches reduce unnecessary prop passing and make code cleaner and more maintainable. Using custom hooks is another effective way to manage shared logic.

# Q11. What is state?
State is a built-in object in React that stores data which can change over time. It controls the behavior and rendering of components. When state changes, React re-renders the component. State is local to the component and cannot be accessed directly by other components. It is mutable and should be updated using setState or useState hook. Proper state management is crucial for building dynamic applications.

# Q12. State vs Props
Props are passed from parent to child and are read-only, while state is managed within the component and can be changed. Props make components reusable, while state handles dynamic data. State changes cause re-rendering, while props reflect external data changes. Both work together to build interactive UIs.

# Q13. What is useState?
useState is a React hook that allows functional components to manage state. It returns an array with the current state value and a function to update it. When the state updates, the component re-renders. useState makes functional components powerful and eliminates the need for class components in most cases.

# Q14. What is useEffect?
useEffect is a hook used to handle side effects like API calls, subscriptions, and DOM updates. It runs after the component renders. It can replace lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount. Dependencies control when useEffect runs.

# Q15. useEffect dependency array
The dependency array tells React when to run useEffect. If empty, it runs once. If dependencies are provided, it runs when they change. Without it, it runs on every render. Proper use prevents performance issues.

# Q16. useEffect vs componentDidMount
componentDidMount is a lifecycle method in class components, while useEffect is used in functional components. useEffect is more flexible and can handle multiple lifecycle behaviors.

# Q17. What is useRef?
useRef is used to persist values across renders without causing re-render. It is commonly used to access DOM elements directly.

# Q18. What is useMemo?
useMemo is used to memoize expensive calculations. It improves performance by avoiding unnecessary recomputation.

# Q19. useCallback vs useMemo
useCallback memoizes functions, while useMemo memoizes values. Both are used for performance optimization.

# Q20. What are custom hooks?
Custom hooks are reusable functions that use React hooks. They help share logic across components and keep code clean.

# Q21. Why key is important in lists?
Keys help React identify which items have changed. Proper keys improve rendering performance and avoid bugs.

# Q22. What is memo?
React.memo is a higher-order component that prevents unnecessary re-renders by memoizing components.

# Q23. React.lazy & Suspense
React.lazy allows dynamic import of components. Suspense shows fallback UI while loading.

# Q24. How to optimize React app?
Use memoization, lazy loading, proper keys, and avoid unnecessary state updates.

# Q25. Controlled vs Uncontrolled components
Controlled components use React state, while uncontrolled use DOM state. Controlled components offer better control and validation.
