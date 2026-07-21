# React 


# Module 1


## Libraries and FrameWorks
- **Libraries** are cllection of reusable code segements targeting specific tasksq usch as jQuery or Lodash.
- **Frameworks** provide a comprehensive structure and guidelines for building entire applications, like angularJS or Vue.js

## Front-End frameworks
- These framewoks specialize in rceating user facing part of web application using HTML, CSS and JavaScript
- Popular front-end frameworks include React, AngularJS, and Vue.js

## React Overview and Features
- React is an open-source JavaScript library developed by Meta for building dynamic user interfaces.
- Key features include component-based architecture, declarative syntax, virtual DOM for performance, one-way data binding, JSX integration, and hooks for managing state and logic.

## Creating a React Project with Vite

- Vite is a modern build tool that improves development speed by bundling Javacript modules only when needed.
- To create a React project with Vite, use the npm create command, select React and JavaScript, then follow terminal instructions to install dependencies and start the development server.

## React Project Folder Structure

- The main directories include node_modules (dependencies), public (static assets and HTML entry point), and src (source code).
- Key files in src are main.jsx (application entry point) and App.jsx (root React component).

## Additional Project Files

- package.json manages project metadata, dependencies, and scripts.
- vite.config.js configures the Vite build process.
-  Other files include .gitignore (Git exclusions), README.md (project info), index.html (web app entry), and eslintrc.cjs (JavaScript linting rules).

## Indroduction to ES6

- Variable Declaration Enhancements

    ES6 introduces let and const to declare variables with block-level scope, improving over the global scope of var and reducing errors in large projects.
    const declares constants whose values cannot be changed, helping maintain immutable data.

- Arrow Functions

    Arrow functions provide a concise syntax for writing functions, allowing shorter and cleaner code.
    They support parameters, implicit returns, and can be used as callbacks, enhancing functional programming style.

- Promises for Asynchronous Operations

    Promises represent the eventual completion or failure of asynchronous operations, replacing complex callback patterns.
    They have states: pending, fulfilled, or rejected, enabling better handling of asynchronous code.

- Classes and Object-Oriented Programming

    ES6 introduces class syntax as a blueprint for creating objects, built on JavaScript prototypes.
    Classes support constructors, inheritance via extends, and super calls, enabling more traditional object-oriented programming patterns in JavaScript.

## Introduction to JSX

- Purpose and Syntax of JSX

    JSX stands for JavaScript XML and looks similar to HTML, using elements enclosed in angle brackets.
    It allows embedding JavaScript expressions within HTML-like syntax to create React elements.

- Compilation and Rendering

    Browsers do not understand JSX directly, so it must be compiled using tools like Babel into standard JavaScript objects.
    React renders these compiled elements to the Document Object Model (DOM).

- Benefits of Using JSX

    JSX is easier to read and modify, especially for those familiar with HTML or markup languages.
    It helps catch errors early during compilation, improves performance through optimization, and enhances security by sanitizing outputs.

- Comparison with Plain JavaScript

    JSX code is more readable and maintainable compared to equivalent JavaScript function calls, combining the clarity of HTML with the power of JavaScript.

## Developing react project with CRA and Vite

- Create React App (CRA)

    CRA is a tool developed by the React team to set up a React development environment with preconfigured dependencies and build tools like Webpack.
    It is reliable and suitable for beginners and small to medium-sized projects, allowing developers to focus on building React components.

- Vite

    Created by Evan You, Vite is a fast build tool that supports multiple JavaScript frameworks, including React.
    It uses native ES module imports and Rollup for bundling, offering faster development server startup, hot module replacement, and optimized production builds with minimal configuration.

- Comparison of CRA and Vite

    CRA projects tend to be larger in size and have more files and folders compared to Vite projects.
    Vite offers faster development times, modern JavaScript support, simpler configuration, and smaller build sizes, making it a compelling choice for larger or more complex projects.

## Components

- React Components Overview

    Components break down the UI into reusable, independent pieces that can be combined into a parent component.
    A React component takes optional input (props) and returns a React object rendered on the screen.


## Component Features and Behavior

   - Components manage properties (props), events, and state to handle data, user interactions, and UI updates.
    State changes allow components to update dynamically based on user actions or other events.


## Types of React Components
  
   - Functional components are JavaScript functions that return JSX; since React 16.8, they can use hooks to manage state.
   - Class components use ES6 classes and include lifecycle methods, state, and props but are now less preferred due to complexity.
    - Higher-order components (HOCs) are functions that take a component and return a new component with added features, enabling logic reuse.

## React Class Components

- A class component is a JavaScript class extending React.Component, encapsulating UI and behavior.
    It uses ES6 class syntax, includes a required render() method that returns JSX, and is exported for use in other files.

- State Management in Class Components

    State holds data that affects rendering and user interaction, initialized in the constructor with this.state.
    State updates are done via this.setState, which merges new state properties, enabling dynamic UI updates.

- Props in Class Components

    Props are read-only data passed from parent to child components, allowing data sharing and method passing.
    Child components access props via this.props, often using destructuring in the render method.

- Event Handling in Class Components

    React handles user interactions like clicks and form submissions using event handlers defined in JSX.
    Event handlers, such as onClick, can call arrow functions to respond to events and update state or trigger actions.


## Introduction to State

- State in Class Components

    State is a built-in JavaScript object in React class components used to store data that can change over time and affect the component's rendering.
    There are two types of state: local state (confined to a single component) and shared state (accessible by multiple components).

- Props in Class Components

    Props (short for properties) are used to pass data from parent components to child components in a unidirectional flow.
    Props are read-only and immutable within the receiving component, making components reusable by allowing them to receive external data.

- Comparison of State and Props

    
     State is managed and modified within the component using methods like setState, while props are passed from parent to child and cannot be changed by the child.
    State controls the component's behavior and rendering dynamically, whereas props provide data and methods from outside the component.


## Class Component lifecycle

- Component Lifecycle Overview

    React class components go through three main phases: mounting, updating, and unmounting.
    The lifecycle describes the component's relationship with the DOM from creation to removal.

- Mounting Phase

    In this phase, the component is instantiated and assigned a default state.
    Key methods include componentWillMount (called before the first render) and componentDidMount (called after the first render).

- Updating Phase

    This phase occurs when component props or state change, triggering re-rendering.
    Important methods are getDerivedStateFromProps (to update state from props), getSnapshotBeforeUpdate (access previous props and state), and componentDidUpdate (for side effects like network requests).

- Unmounting Phase

    The component is removed from the DOM.
    The componentWillUnmount method is called to perform cleanup tasks such as canceling network requests or removing event listeners.

- Render Method

    The render method is called during both mounting and updating phases to update the UI.


# Data Passing Between Components

   - Parent to Child: Using props to pass data from a parent component to its child.
   - Child to Parent: Using callbacks passed as props to send data from a child component back to the parent.
   -  Between Siblings: Typically managed using Redux (not covered in this lecture).



   # Module 2

   ## Functional components

  -  Props and Data Passing

    Props are immutable properties passed from a parent component to a child component to share data.
    Props are accessed in function components via a props object parameter, using dot notation to reference attributes.

- Default Props and Principles

    Default props provide fallback values if a parent component does not supply specific props.
    Key principles of props include reusability, unidirectional data flow, customization, and component composition.

- Event Handling with Props

    The useState hook manages component state, such as toggling UI elements based on user interaction.
    Event handlers like onClick can update state to conditionally render UI elements, demonstrating dynamic behavior with props and state.


### Principles of Component Composition


- Abstraction: Breaking down a large UI into smaller reusable components that encapsulate specific features, improving code organization and maintainability.
    Hierarchy: Arranging components in a parent-child structure to support modular design and organization.

- Key Features and Techniques

    Props and Children: Passing data from parent components to child components to enable dynamic content.
    Higher-Order Components (HOCs): Functions that take components as input and return enhanced components, adding features like state management without modifying the original component.


 - Example of Component Composition

    A blog application example shows separate components for title, author, type, and description, each following a similar structure.
    A higher-order component combines these smaller components into a complex page.
    The main application imports and composes these components with appropriate data to build the front end.
- State Management Concept

    State represents data that can change over time within a component, influencing its behavior and rendering.
    Before hooks, function components could not manage state locally; hooks enable this capability.

- useState Hook Syntax and Usage

    useState is a hook that adds state to function components, returning an array with the current state value and a function to update it.
    Array destructuring assigns these two values to variables, typically named as the state variable and a setter function prefixed with "set".

- Practical Examples of useState

    Example 1: Managing a name state that updates from "John" to "John Doe" on button click, triggering a re-render.
    Example 2: A toggle component that shows or hides a message by toggling a boolean state, with dynamic button text and conditional rendering.

### Functional Component Lifecycle Phases

    React functional components go through four main phases: mounting, updating, unmounting, and error handling.
    Unlike class components, functional components use hooks like useState and useEffect to manage state and side effects.

- Mounting Phase

    During mounting, React initializes the component by running its function body and setting up initial state with useState.
    Side effects such as data fetching are handled with useEffect, which can run once after the initial render when given an empty dependency array.

- Updating Phase

    The updating phase occurs when state or props change, causing React to re-invoke the component function and re-render the UI.
    State updates, such as incrementing a counter with setCount, trigger this re-render to keep the UI in sync with data changes.

- Unmounting Phase

    When a component is removed from the DOM, React runs cleanup operations to free resources like event listeners or timers.
    Cleanup functions returned from useEffect ensure proper resource management, preventing memory leaks.

- Error Handling Phase

    React uses error boundaries to catch errors during rendering or lifecycle methods in child components.
    These boundaries display fallback UI to prevent the entire app from crashing, maintaining overall application stability.

## Testing Overview

  -  Testing involves line-by-line review or running suites of tests to verify code execution and application functionality.
    Advantages include preventing regressions, enabling modular development, and reducing manual checks; disadvantages include extra code maintenance and potential non-critical test failures.


- Approaches to React Component Testing

    Unit testing renders component trees in isolation, often using shallow rendering to test components with default properties.
    End-to-end testing runs the full application in a simulated browser environment to test integrated flows like authentication.

- Testing Process and Tools

    Component tests follow the Arrange-Act-Assert pattern: prepare properties, render and trigger events, then verify outcomes.
    Popular tools include Mocha, Chai, Sinon, Jest, and React Testing Library, with Jest offering integrated features like mocking and snapshot testing.
    React Testing Library encourages testing components as users interact with them, improving test confidence and accessibility.


### DS in react

- Array Basics and Declaration

    Arrays in JavaScript store multiple values in a single variable, defined using square brackets and can hold any data type.
    In React, arrays are commonly used to manage lists of data and can be declared using array literals or stored in component state with the useState hook.

- Traversing and Rendering Arrays in React

    Common methods to traverse arrays include map, forEach, for...of loops, and index-based access.
    The map method is frequently used to render lists by returning JSX elements for each array item, with keys assigned for efficient React rendering.

- Dynamic Array Manipulation and State Management

    Arrays can be dynamically updated by adding or removing items using state and React's setState function.
    Components can conditionally render content based on array contents, such as displaying a list or a message when the array is empty.

## Document Object Model (DOM) Basics

    The DOM represents an HTML document as a tree structure of nodes, including elements, attributes, and text.
    It allows dynamic access and manipulation of a web page's content, structure, and style through programming.

- Virtual DOM in React

    The virtual DOM is an in-memory abstraction of the real DOM used by React to optimize updates.
    React creates a virtual DOM tree on initial render and uses a diffing algorithm to identify minimal changes when state or props update, applying these changes efficiently to the real DOM.

- Advantages of Virtual DOM

    Improves application speed by reducing direct DOM manipulations and re-renders.
    Enables declarative UI development, cross-platform compatibility, effective state management, and easier debugging.
    Supports component reusability and server-side rendering for better performance and SEO.

- Comparison: Normal DOM vs Virtual DOM

    Normal DOM updates directly on the browser, which can be slow for complex pages due to frequent reflows and repaints.
    Virtual DOM updates are batched and minimized, leading to faster and more efficient rendering by only updating necessary parts of the UI.


## Module 3

### Hooks

- Purpose and Advantages of Hooks

    Hooks, introduced in React 16.8, allow function components to use state and lifecycle features previously only available in class components.
    They simplify code, improve readability, reduce complexity, enable code reuse through custom hooks, and can boost component performance.

- Best Practices for Using Hooks

    Hooks must be used only in function components and called at the top level of the component, not inside loops, conditions, nested functions, or regular JavaScript functions.
    React apps using hooks require Node.js version 6 or higher and npm version 5.2 or higher; using create-react-app is recommended for setup.

- Common and Custom Hooks

    Common hooks include useState (state management), useEffect (side effects like data fetching), useContext (context management), and useReducer (state management similar to Redux).
    Custom hooks combine multiple hooks to add unique reusable functionality, named with a "use" prefix, such as useLocalStorage or useAuthentication.

- Role and Function of useEffect and Side Effects

    useEffect allows execution of side effects such as data fetching, event subscriptions, DOM manipulation, or timers when a component loads or updates.
    Side effects are asynchronous actions that impact the application state or UI, triggered automatically without separate calls.

- Dependencies in useEffect

    An empty dependency array makes useEffect run only once on component mount.
    Specifying variables in the dependency array causes useEffect to run whenever those variables change.
    Omitting the dependency array runs useEffect after every render, which can lead to repeated executions.

- Custom Hooks in React

    Custom hooks encapsulate reusable logic that can be shared across components.
    Example: a useToggle custom hook manages a boolean state and toggle function, used in a ToggleButton component to switch between on/off states on click.

 ###   External Services and APIs

    External services are programs or platforms outside your app that provide features or data over a network.
    APIs (Application Programming Interfaces) allow your app to communicate with these services to get data or perform operations.

- Fetching Data with Fetch API

    The Fetch API sends HTTP requests to external URLs and returns promises.
    You handle the response by parsing JSON data and managing errors with then and catch methods.

- Using Axios Library

    Axios is a JavaScript library for HTTP requests that simplifies the process.
    It automatically parses JSON responses and requires less code compared to Fetch, while also handling errors effectively.


### Froms

- Purpose and Components of Forms

    Forms enable user interaction with data on web pages through fields like text boxes, drop-downs, radio buttons, and checkboxes.
    Forms require input fields, submission logic to control when data is accepted, and validation rules to ensure data correctness.

- Controlled vs. Uncontrolled Components

    Uncontrolled components rely on the browser to manage form element state, storing values in the DOM, and use refs to access input values.
    Controlled components manage form data explicitly through React state, requiring event handlers and state updates via methods like setState or hooks.

- React Hook Form Library

    React Hook Form simplifies form state management and validation, reducing code complexity.
    It improves performance by minimizing unnecessary re-rendering of form components.


### Introduction to Redux
- Component vs. Application State

    Component state holds data specific to a single UI component, while application state contains data relevant to the entire app.
    Application state can be accessed from any component, enabling features like a shared shopping cart accessible throughout an e-commerce app.

P- urpose and Use of Redux

    Redux centralizes application state management, replacing individual component states with a global store.
    It is especially useful in large applications with many components that need to share data across different parts of the UI.

- Benefits of Using Redux

    Simplifies code by reducing the complexity of passing data through component trees.
    Improves code readability and maintainability by having a single source of truth for state.
    Enhances performance by minimizing unnecessary page renders and updating only the parts of the UI that change.

- Core Redux Concepts

    Redux manages application state at a global level, not within individual components, treating component properties as immutable.
    Key elements include the store (holds all current states), actions (objects indicating state update needs), and reducers (functions defining how state changes).

- Redux Architecture and Workflow

    Actions are created by action creators and dispatched to the store, which uses the action's type to select the appropriate reducer.
    The reducer, a pure function, receives the current state and action to compute and return a new state without side effects.

- Practical Example and Benefits

    In an e-commerce cart example, adding items triggers an action creator that dispatches an action to update the cart state in the store via a reducer.
    This architecture ensures predictable state changes, easier debugging, and clearer code maintenance by separating action descriptions from state update logic.

### Synchronous vs Asynchronous Operations

    Synchronous operations block the next operation until the current one finishes, while asynchronous operations run in parallel, allowing multiple processes to occur simultaneously.
    Asynchronous behavior is preferred for tasks like network requests or heavy computations to keep the user interface responsive.

- Challenges of Async in Redux

    Redux requires synchronous state updates, but many real-world actions (e.g., fetching data) are asynchronous, which can cause complications.
    Middleware intercepts actions to manage async operations, delaying dispatch until async tasks complete, thus maintaining Redux’s synchronous flow.

 - Thunk and Saga Middleware

    Thunk middleware allows action creators to return functions that perform async operations and dispatch actions based on results; it is simpler but less scalable and requires careful concurrency handling.
    Saga middleware uses ES6 generator functions to handle async flows by pausing and resuming execution, offering better scalability, easier testing, and debugging but with a steeper learning curve.
### Redux and flow

- State Change and Challenges

    In React, component state stores properties, and changes trigger re-rendering of the DOM.
    Managing state becomes complex as applications grow, especially with data transfer between components and prop chains.

- Redux Overview and Elements

    Redux is a JavaScript library that manages application state centrally, commonly used with React but also compatible with other frameworks.
    Key Redux elements include the central store (state tree), actions (objects describing changes), reducers (functions updating state immutably), and subscriptions (components updating on state changes).

- Data Flow and Advantages of One-Way Binding

    Redux enforces unidirectional data flow: user interactions dispatch actions, reducers update state, and components re-render with new state.
    One-way data flow simplifies state management, improves performance over two-way binding, and makes large front-end applications more manageable.

### Redux toolkit


- Redux Toolkit Overview

    RTK is an official package from the Redux team designed to reduce boilerplate and make Redux easier to use in React applications.
    It provides utilities like configureStore for setting up the store with middleware and DevTools, and createSlice for defining reducers and actions with immutable state updates.


- Key Redux Toolkit Concepts

    A slice represents a portion of application state along with its reducer logic, action creators, and initial state, all defined using createSlice.
    The Redux store holds the complete state tree and is created using configureStore, which combines slice reducers and manages state access and updates.


- Relationship Between Store and Slices

    Multiple slices define different parts of the state; these are combined in the store to form the full application state.
    Actions dispatched to the store are routed to the appropriate slice reducers to update state accordingly.

- Example Application Structure

    Components like ProductQuantity.jsx and CartValue.jsx interact with the Redux store using React Redux hooks (useSelector, useDispatch).
    CounterSlice.jsx defines state and reducers for product quantity, Store.jsx configures the Redux store, and Main.jsx wraps the app with the Redux Provider.