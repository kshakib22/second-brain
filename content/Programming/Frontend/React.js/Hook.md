
React Hooks are functions that let you "hook into" React features (like state and lifecycle methods) from functional components. They were introduced in React 16.8 to allow functional components to have state and side effects, making class components largely unnecessary for most use cases.

---

### Why Hooks?

* **No Classes:** Write React components as plain JavaScript functions.
* **Reusability:** Reuse stateful logic without changing your component hierarchy (no more render props or HOCs for this purpose).
* **Simpler Code:** Often lead to less code and easier-to-understand components compared to class components with their `this` bindings and lifecycle methods.
* **Improved Readability:** Logic related to a single concern (e.g., data fetching, form handling) can be kept together.

---

### Core Hooks

1.  **`useState()`**
    * **Purpose:** Add state variables to functional components.
    * **Syntax:** `const [stateVariable, setStateVariable] = useState(initialValue);`
    * **Example Use Cases:** Managing input values, toggling UI elements, counters.

2.  **`useEffect()`**
    * **Purpose:** Perform side effects in functional components (e.g., data fetching, subscriptions, manually changing the DOM).
    * **Syntax:** `useEffect(() => { /* side effect code */ }, [dependencies]);`
    * **Execution:**
        * Runs after every render by default.
        * With an empty dependency array `[]`, it runs once after the initial render (like `componentDidMount`).
        * With dependencies, it runs when any dependency changes (like `componentDidUpdate`).
    * **Cleanup:** Can return a cleanup function to run before the component unmounts or before the effect runs again (like `componentWillUnmount`).

3.  **`useContext()`**
    * **Purpose:** Consume values from React's Context API. Avoids "prop drilling."
    * **Syntax:** `const value = useContext(MyContext);`
    * **Use Cases:** Theming, user authentication status, global state accessible deeply in the component tree.

4.  **`useRef()`**
    * **Purpose:** Create a mutable `ref` object that persists across renders. Useful for directly accessing DOM nodes or storing any mutable value that doesn't trigger a re-render when changed.
    * **Syntax:** `const myRef = useRef(initialValue);`
    * **Use Cases:** Managing focus, text selection, media playback, integrating with third-party DOM libraries.

5.  **`useReducer()`**
    * **Purpose:** An alternative to `useState` for more complex state logic, especially when state transitions depend on the previous state or involve multiple sub-values. Similar to Redux.
    * **Syntax:** `const [state, dispatch] = useReducer(reducerFunction, initialState);`
    * **Use Cases:** Complex forms, shopping carts, managing state that involves many actions.

6.  **`useCallback()`**
    * **Purpose:** Memoize (cache) a function. Returns a memoized version of the callback that only changes if one of the dependencies has changed. Prevents unnecessary re-renders of child components that receive the function as a prop.
    * **Syntax:** `const memoizedCallback = useCallback(() => { /* ... */ }, [dependencies]);`

7.  **`useMemo()`**
    * **Purpose:** Memoize (cache) a computed value. Returns a memoized value that only recomputes when one of the dependencies has changed. Prevents expensive calculations on every render.
    * **Syntax:** `const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);`

---

### Rules of Hooks

* **Only Call Hooks at the Top Level:** Don't call Hooks inside loops, conditions, or nested functions.
* **Only Call Hooks from React Functions:** Call them from React functional components or custom Hooks.

---

### Custom Hooks

* **Purpose:** Extract reusable stateful logic from components into a separate function.
* **Convention:** Custom Hook names must start with `use` (e.g., `useFetch`, `useLocalStorage`).
* **Benefits:** Promotes code sharing, keeps components cleaner, improves testability.