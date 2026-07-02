# React 

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