---
title: "React.js Conceptual Questions"
slug: reactjs-conceptual-questions

---

## 1\. What is React, and why is it used?

React is a JavaScript library created by **Meta** (formerly Facebook) for building user interfaces. It allows developers to create complex UIs by combining smaller, reusable components. React uses a **virtual DOM** to improve performance and provides a component-based architecture to manage state and props effectively.

---

## 2\. What are the main features of React?

* **Virtual DOM** for efficient updates.
    
* **Component-based architecture** for reusable and modular code.
    
* **Unidirectional data flow** to simplify data management.
    
* **Hooks** for state and lifecycle management in functional components.
    
* **JSX** for writing HTML-like syntax in JavaScript.
    

---

## 3\. What is the difference between functional and class components?

* **Functional Components**:
    
    * Written as simple JavaScript functions.
        
    * Use hooks like `useState()` and `useEffect()` for state and lifecycle management.
        
    * Easier to write and maintain.
        
* **Class Components**:
    
    * Written using ES6 class syntax.
        
    * Require lifecycle methods like `componentDidMount()` for managing state and side effects.
        
    * More verbose compared to functional components.
        

**Preferred**: Functional components (due to simplicity and hooks introduced in React v16.8).

---

## 4\. What are Props and State in React?

* **Props**:
    
    * Passed from parent to child components.
        
    * Immutable and used to pass data or functions.
        
* **State**:
    
    * Managed within a component.
        
    * Mutable and used to handle dynamic data.
        

---

## 5\. How does the Virtual DOM work?

React uses the virtual DOM to enhance performance. The process involves:

1. Re-rendering the virtual DOM when state or props change.
    
2. Comparing the updated virtual DOM with the previous version (diffing).
    
3. Updating only the changed elements in the real DOM.
    

---

## 6\. What is the purpose of the `key` prop in lists?

The `key` prop helps React identify which items in a list have changed, been added, or removed. Keys should be unique and stable, typically using object IDs. Avoid using array indexes as keys unless necessary.

---

## 7\. What are React Hooks?

Hooks are functions introduced in React v16.8 that allow functional components to use state and lifecycle features. Common hooks include:

* `useState()`: For managing state.
    
* `useEffect()`: For handling side effects.
    
* `useContext()`: For accessing context values.
    

---

## 8\. What are the React lifecycle methods, and when are they used?

React components go through three lifecycle phases:

* **Mounting**:
    
    * `constructor()`
        
    * `getDerivedStateFromProps()`
        
    * `render()`
        
    * `componentDidMount()`
        
* **Updating**:
    
    * `shouldComponentUpdate()`
        
    * `render()`
        
    * `componentDidUpdate()`
        
* **Unmounting**:
    
    * `componentWillUnmount()`
        

For functional components, hooks like `useEffect()` are used instead of lifecycle methods.

---

## 9\. When would you use `useEffect`?

* To fetch data from an API.
    
* To set up subscriptions or timers.
    
* To handle cleanup (like removing event listeners) using the return function in `useEffect`.
    

---

## 10\. What is Context API, and why is it used?

The **Context API** is used to manage the global state by avoiding prop drilling. It allows components to access shared data directly, such as themes, authentication status, or user settings.

---

## 11\. How does React handle state management?

React provides several ways to manage state:

* **Component-level state** using `useState` or `useReducer`.
    
* **Context API** for global state shared across components.
    
* **Third-party libraries** like Redux or Zustand for complex state management.
    

---

## 12\. What is Redux, and why use it?

Redux is a state management library that centralizes application state in a global store. It helps in managing shared state efficiently, especially when:

* Multiple components require access to the same data.
    
* The application has complex state interactions.
    

---

## 13\. What are the building blocks of Redux?

* **Store**: Centralized state container.
    
* **Actions**: Plain JavaScript objects describing changes.
    
* **Reducers**: Pure functions that specify how the state changes in response to actions.
    

---

## 14\. What is the `useReducer` hook, and when would you use it?

`useReducer` is a hook used for complex state logic. It provides a way to manage state using actions and reducers, similar to Redux but scoped to a component.

---

## 15\. How do you optimize performance in React?

* Use **memoization** with `React.memo` or `useMemo`.
    
* Implement **lazy loading** for components using `React.lazy` and `Suspense`.
    
* Avoid unnecessary re-renders by using `React.PureComponent` or `useCallback`.
    
* Use **keys** efficiently in lists.
    

---

## 16\. How do you fetch data in React, and where do you handle API calls?

* Fetch data using `fetch` or libraries like Axios.
    
* Handle API calls inside `useEffect()` for functional components or `componentDidMount()` for class components.
    

---

## 17\. What is the difference between `useEffect` and `useLayoutEffect`?

* **useEffect**: Runs asynchronously after rendering, suitable for data fetching or subscriptions.
    
* **useLayoutEffect**: Runs synchronously after rendering but before the DOM is updated, suitable for layout adjustments.
    

---

## 18\. What is the importance of React's unidirectional data flow?

Unidirectional data flow ensures that data flows from parent to child components, making state management predictable and debugging easier.

---

## 19\. How do you handle error boundaries in React?

Error boundaries are implemented using class components with lifecycle methods like `componentDidCatch()` and `getDerivedStateFromError()`. They catch JavaScript errors in the component tree and prevent the app from crashing.

---

## 20\. Explain the difference between controlled and uncontrolled components.

* **Controlled Components**:
    
    * Manage form data using state.
        
    * Data flows through React state.
        
* **Uncontrolled Components**:
    
    * Use refs to manage form data.
        
    * Data flows through the DOM.
        

---