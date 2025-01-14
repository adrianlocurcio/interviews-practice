# REACT

## TABLE OF CONTENTS

- [Concepts](#concepts)
  - What is React?
  - What is COP (component oriented programming)?
  - What is Immutability and why it is important in React?
  - What is the Virtual DOM?
  - What is the Reconciliation in React?
- [Redux](#redux)
  - What is Redux?
  - What is a HOC (High order component)?
  - What is a Redux Middleware?
  - What is redux-saga?
  - What is redux-thunk?
- [react-native](#react-native)
  - What is react-native?
  - What is different in react-native from react?
- [Hooks](#hooks)
  - What are React Hooks?
  - What are the advantages of using hooks?
  - The useState hook
  - The useEffect hook
  - The useContext hook
  - The useMemo hook
  - The useCallback hook
  - What is the difference between useMemo and useCallback?
  - The useRef hook
  - The useReducer hook
- [Frameworks](#frameworks)
  - Create React App
  - NextJS
  - What is client-side rendering (CSR)?
  - What is Server-side rendering (SSR)?
  - What are the differences between CSR and SSR?

<a name="concepts"/>

## Concepts

### What is React?

React is a javascript library for the frontend. It is based on the Component Oriented Programming paradigm. It is very useful for building interactive user interfaces.

In React, you have a state with important data in your app that can change dynamically, and you can show different views depending on each state. Another important topic is that it uses a virtual DOM.

### What is COP (component oriented programming)?

Component Oriented Programming (COP) is a technique for software development that consist on combining independent entitied, called components, in order to build an app.

### What is Immutability and why it is important in React?

In programming, immutability refers to not changing the values of certain entities. Specifically, if an object is immutable means its state cannot be modified after its creation.

In React, immutability is related to the reconciliation process: it is easier and faster to tell that something changed if the old object is different than the new one, instead of figuring out if any prop inside the original object has been altered.

### What is the Virtual DOM?

The VirtualDom, like the DOM, is a node tree that list the webpage elements as objects. reactJS uses the VirtualDOM to compare the changes in the state and props and determinate which updates send to the real DOM for repainting or re-rendering the UI.

### What is the Reconciliation in React?

It is a process of React for updating the UI in a fast way. It is related to concepts as **Browser DOM**, **Virtual Dom** and **Diffing algorithm**.

As explained on the previous bullet, when there are changes on state or props, React creates a **new Virtual DOM** and compares it with the **old Virtual DOM** using a **Diffing algorithm**. Then, if there are differences, it updates the real **Browser DOM** with the minimum required changes. It is of course more efficient than just updating all the real Browser DOM every time.

Source: https://en.reactjs.org/docs/reconciliation.html

<a name="redux"/>

## Redux

### What is Redux?

- Redux is a store manager in reactJS applications. It is a structure that helps to clarify the code when your app scalates. In this structure, there is a `store` where all state variables of all the components can be stored. Then, the components can `connect` to that store and access to them. That way, when a component needs to access a state variable, there is no need to pass it as a prop from parent to child (sometimes in multiple levels) or refactor DOM structure. The component just access to the store and access to the variable.
- Redux is also an architecture that is related to the data flow direction. The data flow is unidirectional. In a Redux app, the data flow is:
  - Initial situation: the `state` describes the condition of the app at a specific point and the `UI` is rendered based on that state.
  - When something happens in the app, such as a user clicking a button, an action is created by an `actionCreator`. Then, that action is `dispatched` to the Redux store, like `dispatch({type: 'SAY_HELLO'})`.
  - The store runs the `reducer` function again with the previous state and the current action, and saves the return value as the new state.
  - The UI renders the changes based on the new `state`. So we go back to the beginning of the cycle.

### What is a HOC (High order component)?

A High Order Component (HOC) is a function that takes a component as parameter and returns another component. For example, the `connect` function in `Redux` is a HOC.

### What is a Redux Middleware?

It is a tool that allows you to intercept every action sent to the reducer so you can make changes to the action or cancel the action. Middleware helps you with logging, error reporting, making asynchronous requests, among other possibilities.

### What is redux-saga?

It is a redux middleware. It is a javascript library that aims to make app side effects easier to manage, to test, to handle and more efficient. The mental model is like each saga is a separated thread only responsible for side effects. It uses ES6 generators.

### What is redux-thunk?

It is a Redux middleware that allows to handle asynchronicity (because vanilla Redux does not handle asynchronicity).

In redux-thunk it is posible to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods dispatch and getState as parameters.

<a name="react-native"/>

## react-native

### What is react-native?

It is a JS framework for writing mobile apps for iOS and Android. It uses reactJS principes and syntax.

### What is different in react-native from react?

- In react-native there is no DOM. Instead, react-native uses a native API to render components.
- react-native does not use HTML or CSS. Instead, there are native views.
- The navigation: in react-native there is a stack of views and the user navigates throw those views.
- All stuff related to hardware usage: camera, microphone, GPS, etc.

<a name="hooks"/>

## Hooks

### What are React Hooks?

Hooks are the new feature introduced in the React 16.8 version. It allows you to use state and other React features without writing a class. Hooks are the functions which "hook into" React state and lifecycle features from function components. It does not work inside classes.

Source: https://en.reactjs.org/docs/hooks-intro.html

### What are the advantages of using hooks?

- Cleaner code: easier to read and write.
- Re-usability: since a hook extract stateful logic from a component, it can be tested independently and reused in other components.
- More efficient: there are certain tools like `usememo` and `useCallback` hooks related to performance, and the `array dependency` in `useEffect` that allows to execute certain code when a specific or specific prop is updated (not like the `componentDidUpdate` in React classes that fires when any prop or state is changed).

### The useState hook

The `useState` hook creates a piece of state for the component. Calling the hook returns the current value of that piece of state, and a method to update it, in the form of an array. This hook accepts one parameter that is the `initialValue`. If the initial value is expensive to compute, you may want to wrap it in a function. It looks like this:

```
const [value, setValue] = useState(initialValue);
```

### The useEffect hook

The `useEffect` hook lets you perform side effects in function components. For example, changing the DOM, fetching some data, subscribing to things that emit events, among other effects. It serves a purpose similar to some lifecycle methods of class components: `componentDidMount`, `componentDidUpdate` or `componentWillUnmount`. It looks like this:

```
/**
* effect is a function that performs the effect
* dependencies is an array of values on which the effect depends
**/
useEffect(effect [, dependencies]);
```

Some effects might require cleanup so they return a function like this example:

```
useEffect(() => {
  // add an event listener

  return () => {
    // remove the event listener
  };
}, []);
```

Source: https://en.reactjs.org/docs/hooks-effect.html

### The useContext hook

The `useContext` hook is used to create common data that can be accessed throughout the component hierarchy without passing the props down manually to each level. Context defined will be available to all the child components without involving `props`.

Example:

```
import { useState, createContext, useContext } from "react";

const UserContext = createContext();

function Component1() {
  const [user, setUser] = useState("Jesse Hall");

  return (
    <UserContext.Provider value={user}>
      <h1>{`Hello ${user}!`}</h1>
      <AnotherChild />
    </UserContext.Provider>
  );
}

const AnotherChild = () => {
  const user = useContext(UserContext);

  return (
    <div>{`Hello ${user} again!`}</div>
  );
}
```

Source: https://en.reactjs.org/docs/hooks-reference.html#usecontext

### The useMemo hook

The `useMemo` hook returns a memoized value (it is like caching a value so that it does not need to be recalculated). The useMemo Hook only runs when one of its dependencies update. Based on that, this tool can improve performance.

Example:

`const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);`

Source: https://en.reactjs.org/docs/hooks-reference.html#usememo

### The useCallback hook

The `useCallback` hook returns a memoized callback.

It receives two parameters: a callback and an array of dependencies. It will return a memoized version of the callback that only changes if one of the dependencies has changed. This is useful when passing callbacks to optimized child components that rely on reference equality to prevent unnecessary renders.

Example:

`const memoizedCallback = useCallback(myFunction, [a, b]);`

Source: https://en.reactjs.org/docs/hooks-reference.html#usecallback

### What is the difference between useMemo and useCallback?

The main difference is that `useMemo` returns a memoized value while `useCallback` returns a memoized function.

In code, `useCallback(fn, deps)` is equivalent to `useMemo(() => fn, deps).`

### The useRef hook

The `useRef` hook allows to persist values between renders. It can be used to store a mutable value that does not cause a re-render when updated. It can be used to access a DOM element directly. It returns a ref object with a `current` property that has a mutable value.

Example:

`const refContainer = useRef(initialValue);`

Source: https://en.reactjs.org/docs/hooks-reference.html#useref

### The useReducer hook

The `useReducer` hook ia an alternative to `useState`. It accepts a reducer of type `(state, action) => newState`, and returns the current state paired with a dispatch method (similar to Redux concepts).

Writing: `const [state, dispatch] = useReducer(reducer, initialArg, init);`

Example:

```
const initialState = {count: 0};

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}
```

Source: https://en.reactjs.org/docs/hooks-reference.html#usereducer

<a name="frameworks"/>

## Frameworks

### Create React App

complete

### NextJS

complete

### What is client-side rendering (CSR)?

complete

### What is Server-side rendering (SSR)?

complete

### What are the differences between CSR and SSR?

complete
