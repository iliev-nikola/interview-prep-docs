# React topics

Source:
- https://reactjs.org/
- https://www.udemy.com/course/react-the-complete-guide-incl-redux/
- https://redux.js.org/

## Basics

### Getting started with React

- What is React?
```a
React is a JavaScript library for building user interfaces.
```

- What are its advantages?
```a
- Easy creation of dynamic applications: React makes it easier to create dynamic web applications because it requires less coding and offers more functionality, as opposed to JavaScript, where coding often gets complex very quickly.

- Improved performance: React uses Virtual DOM, thereby creating web applications faster. Virtual DOM compares the components’ previous states and updates only the items in the Real DOM that were changed, instead of updating all of the components again, as conventional web applications do. 

- Reusable components: Components are the building blocks of any React application, and a single app usually consists of multiple components. These components have their logic and controls, and they can be reused throughout the application, which in turn dramatically reduces the application’s development time.

- Unidirectional data flow: React follows a unidirectional data flow. This means that when designing a React app, developers often nest child components within parent components. Since the data flows in a single direction, it becomes easier to debug errors and know where a problem occurs in an application at the moment in question.

- Small learning curve: React is easy to learn, as it mostly combines basic HTML and JavaScript concepts with some beneficial additions. Still, as is the case with other tools and frameworks, you have to spend some time to get a proper understanding of React’s library.

- It can be used for the development of both web and mobile apps: We already know that React is used for the development of web applications, but that’s not all it can do. There is a framework called React Native, derived from React itself, that is hugely popular and is used for creating beautiful mobile applications. So, in reality, React can be used for making both web and mobile applications.

- Dedicated tools for easy debugging: Facebook has released a Chrome extension that can be used to debug React applications. This makes the process of debugging React web applications faster and easier.
```

- What is JSX?
```a
JSX stands for JavaScript XML. It is simply a syntax extension of JavaScript. It allows us to directly write HTML in React (within JavaScript code). It is easy to create a template using JSX in React, but it is not a simple template language instead it comes with the full power of JavaScript.
It is faster than normal JavaScript as it performs optimizations while translating to regular JavaScript. Instead of separating the markup and logic in separated files, React uses components for this purpose. We will learn about components in detail in further articles. 
```

- What elements are there in React (React Vocabulary)?
```a
- Elements - React elements are the building blocks of React applications. One might confuse elements with a more widely known concept of “components”. An element describes what you want to see on the screen. React elements are immutable.

- Components - React components are small, reusable pieces of code that return a React element to be rendered to the page. The simplest version of React component is a plain JavaScript function that returns a React element.

- props - props are inputs to a React component. They are data passed down from a parent component to a child component. Remember that props are readonly. They should not be modified in any way.

- state - The most important difference between state and props is that props are passed from a parent component, but state is managed by the component itself. A component cannot change its props, but it can change its state.

- keys - A “key” is a special string attribute you need to include when creating arrays of elements. Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside an array to give the elements a stable identity.

- Refs - React supports a special attribute that you can attach to any component. The ref attribute can be an object created by React.createRef() function or a callback function, or a string (in legacy API). When the ref attribute is a callback function, the function receives the underlying DOM element or class instance (depending on the type of element) as its argument. This allows you to have direct access to the DOM element or component instance.
```

- How is it different from Angular?

| React | Angular |
| ----- | ------- |
| React is a javascript library that allows you to build UI components. | AngularJS is a structural framework for developing dynamic web apps. |
| React is based on Virtual DOM. | Angular JS is based on MVC (Model View Controller). |
| React is based on Javascript. | Angular is based on Typescript. |
| React allows adding javascript library to the source code. | AngularJS doesn’t provide adding javascript library to the source code. |
| React requires a set of tools to perform different types of testing. | AngularJS provides testing and debugging for a complete project with a single tool. |

- What are React DevTools?
```a
React Developer Tools is a Chrome DevTools extension for the open-source React JavaScript library. It allows you to inspect the React component hierarchies in the Chrome Developer Tools.

You will get two new tabs in your Chrome DevTools: "⚛️ Components" and "⚛️ Profiler".

The Components tab shows you the root React components that were rendered on the page, as well as the subcomponents that they ended up rendering.

By selecting one of the components in the tree, you can inspect and edit its current props and state in the panel on the right. In the breadcrumbs you can inspect the selected component, the component that created it, the component that created that one, and so on.

If you inspect a React element on the page using the regular Elements tab, then switch over to the React tab, that element will be automatically selected in the React tree.

The Profiler tab allows you to record performance information.
```

### Virtual DOM

- How is Virtual DOM working?
```a
In simple words, virtual DOM is just a copy of the original DOM kept in the memory and synced with the real DOM by libraries such as ReactDOM. This process is called Reconciliation.

Virtual DOM has the same properties that of the Real DOM, but it lacks the power to directly change the content of the screen.

So when there is a update in the virtual DOM, react compares the virtual DOM with a snapshot of the virtual DOM taken right before the update of the virtual DOM.

With the help of this comparison React figures out which components in the UI needs to be updated. This process is called diffing. The algorithm that is used for the diffing process is called as the diffing algorithm.

Once React knows which components has been updated, then it replaces the original DOM nodes with the updated DOM node.
```

- What is `reconciliation`?
```a
The reconciliation process makes React work faster. Reconciliation is the process through which React updates the Browser DOM.

Reconciliation is the process in which React kind of appears to reload data or the whole app on updates, when really it doesn’t. It’s the API that handles what changes on every update. It’s also part of the way in which React solved traversing the DOM in linear rather than exponential complexity.
```

- What are the differences between Real DOM and Virtual DOM?
```a
Real Dom:
The DOM is an abstraction of a page’s HTML structure. It takes HTML elements and wraps them in an object with a tree-structure — maintaining the parent/child relationships of those nested HTML elements. This provides an API that allows us to traverse nodes (HTML elements) and manipulate them in a number of ways — such as adding nodes, removing nodes, editing a node’s content, etc.

Virtual DOM:
The Virtual DOM is a light-weight abstraction of the DOM. You can think of it as a copy of the DOM, that can be updated without affecting the actual DOM. It has all the same properties as the real DOM object, but doesn’t have the ability to write to the screen like the real DOM. The virtual DOM gains it’s speed and efficiency from the fact that it’s lightweight. In fact, a new virtual DOM is created after every re-render.
```

| Real DOM | Virtual DOM |
| -------- | ----------- |
| DOM is a language-neutral interface allowing programs and scripts to dynamically access and update multiple objects like content, structure, and style of a document. | Is a collection of modules designed to provide a declarative way to represent the DOM for an application. |
| The DOM represents the document as nodes and objects. | A virtual DOM object is a representation of a DOM object, like a lightweight copy. |
| It is an object-oriented representation of a web page, modified with a scripting language like JavaScript. | Virtual DOM is ideal for mobile-first applications. |

- Is the Shadow DOM the same as Virtual DOM?
```a
No, they are different. The Shadow DOM is a browser technology designed primarily for scoping variables and CSS in web components. The virtual DOM is a concept implemented by libraries in JavaScript on top of browser APIs.
```

| Virtual DOM | Shadow DOM |
| ----------- | ---------- |
| It revolves around solving performance issues. | It revolves around the concept of encapsulation. |
| It is a complete representation of an actual DOM. | It is not a complete representation of the entire DOM. |
| It groups together several changes and does a single re-render instead of many small ones. | It adds a subtree of DOM elements into the rendering of a document, instead of adding it to the main document’s DOM tree. |
| It creates a copy of the whole DOM object. | It creates small pieces of the DOM object having their own, isolated scope. |
| It does not isolate the DOM. | 	It isolates the DOM. |
| It does not help with CSS scoping. | It helps with CSS scoping. |

### Components

- What is the difference between Element and Component?
```a
1. React Element - It is a simple object that describes a DOM node and its attributes or properties you can say. It is an immutable description object and you can not apply any methods on it:
```
```
<button class="blue"></button>
```
```a
2. React Component - It is a function or class that accepts an input and returns a React element. It has to keep references to its DOM nodes and to the instances of the child components:
```
```
const SignIn = () => (
  <div>
   <p>Sign In</p>
   <button>Continue</button>
   <button color='blue'>Cancel</button>
  </div>
);
```

- Different kind of components - Class vs. Functional / Stateful vs. Stateless / Smart vs. Dumb
```a
1. Class vs. Functional components:
```
<table>
<thead>
<tr>
<th>Class components</th>
<th>Functional components</th>
</tr>
</thead>
<tbody>
<tr>
<td>A class component requires you to extend from React. Component and create a render function which returns a React element.</td>
<td>A functional component is just a plain JavaScript function that accepts props as an argument and returns a React element.</td>
</tr>
<tr>
<td>It must have the render() method returning HTML</td>
<td>There is no render method used in functional components.</td>
</tr>
<tr>
<td>Also known as Stateful components because they implement logic and state.</td>
<td>Also known as Stateless components as they simply accept data and display them in some form, that they are mainly responsible for rendering UI.</td>
</tr>
<tr>
<td>React lifecycle methods can be used inside class components (for example, componentDidMount).</td>
<td>React lifecycle methods (for example, componentDidMount) cannot be used in functional components.</td>
</tr>
<tr>
<td>It requires different syntax inside a class component to implement hooks. </br>

```
constructor(props) {
  super(props);
  this.state = {name: ‘ ‘}
}
```

</td>
<td>Hooks can be easily used in functional components. example: </br>

```
const [name,SetName]= React.useState(‘ ‘);
```

</td>
</tr>
</tbody>
</table>

```a
2. Stateful vs. Stateless components:
Stateful component:
- A component that manages the state in class-based with state or functional with useState.
- In some component, the data keeps changing, for example, watching the cricket score etc.
- In most of the cases, the class-based components extend react component.
- Stateful components can use react life cycle hooks
- In stateful components it good to use the this instance

Stateless component:
- A component that has no internal state management in it.
- In some component, the data remains the same, for example, showing the static data.
- Function components are simply functions that receive the props and return the JSX code.
- Stateless components can not use the react life cycle hooks
- Here need not to use this instance, they just receive the props as an argument

When would you use a stateless component?
- When you just need to present the props
- When you don’t need a state, or any internal variables
- When creating element does not need to be interactive
- When you want reusable code

When would you use a stateful component?
- When building element that accepts user input
- ..or element that is interactive on page
- When dependent on state for rendering, such as, fetching data before rendering
- When dependent on any data that cannot be passed down as props
```

```a
3. Smart vs. Dumb components:
Dumb Components:
Dumb components are also called ‘presentational’ components because their only responsibility is to present something to the DOM. Once that is done, the component is done with it. No keeping tabs on it, no checking in once in a while to see how things are going. Nope. Put the info on the page and move on.
The components themselves only have a render() method (they don’t need any others) and are often just Javascript functions. They don’t have internal state to manage. They wouldn’t know how to change the data they are presenting if they were asked. Ignorance is bliss.

Smart Components:
Smart components (or container components) on the other hand have a different responsibility. Because they have the burden of being smart, they are the ones that keep track of state and care about how the app works.
Using the container design pattern, the container components are separated from the presentational components and each handles their own side of things. The container components do the heavy lifting and pass the data down to the presentational components as props.
They are class-based components and have their own state defined in their constructor() functions.
```

- What is the required method to be defined for a class component?
```a
It must have the render() method returning HTML
```

- Component interactions - parent to children / children to parent
```a
1. Parent to child:
When you need to pass data from a parent to child class component, you do this by using props.

2. Child to parent:
Passing the data from the child to parent component is a bit trickier. In order to do this, you need to do the following steps:
- Create a callback function in the parent component. This callback function will get the data from the child component.
- Pass the callback function in the parent as a prop to the child component.
- The child component calls the parent callback function using props.
```

- What is `state`?
```a
React components has a built-in state object.

The state object is where you store property values that belongs to the component.

When the state object changes, the component re-renders.
```

- What are `props`?
```a
Props are Read-Only

Props are arguments passed into React components.

Props are passed to components via HTML attributes.

React Props are like function arguments in JavaScript and attributes in HTML.
```

- Higher order components
```a
A higher-order component (HOC) is an advanced element for reusing logic in React components. Components take one or more components as arguments, and return a new upgraded component. Sounds familiar, right? They are similar to higher-order functions, which take some functions as an argument and produce a new function.

HOCs are commonly used to design components with certain shared behavior in a way that makes them connected differently than normal state-to-props pattern.

A HOC is structured like a higher-order function:
- It is a component.
- It takes another component as an argument.
- Then, it returns a new component.
- The component it returns can render the original component that was passed to it.
```

- Controlled components
```a
Controlled components in React are those in which form data is handled by the component’s state.

Forms are used to store information in a document section. The information from this form is typically sent to a server to perform an action. This data is held by form input elements and control elements, such as input, select, textarea, etc., which maintain and control their states or values.

Each form element contains a value. The value may be typed (input, textarea) or selected (checkbox, select, radiobutton, etc) by the user or browser. When the element’s value is changed (triggered by the act of typing or selecting), it is updated accordingly.

You can get the value of an element using the .value property in its HTMLElement instance. You can also use the .value property to set values in the form elements.
```

### Event handling

- Difference between HTML and React event handling
```a
- In HTML, we specify event in html tags like onclick, onsubmit etc. and pass the string that contain the parenthesis at the end.
- In html, we can also add them afterword using external javascript using addEventListener.
- In React, we specify event at the time of creating our component.
- we use camel case convention in React i. e. onClick, onSubmit.
- In React, we bind them using method name only like onClick={greet}.
- addEventListener cannot be used in React component.
```

| HTML | React |
| ---- | ----- |
| we specify event using “onclick”,”onsubmit”which is the normal convention.  | We specify the event using  “onClick”,”onSubmit” likewise which is camel case convention. |
| We bind or provide the listener in form of the string. | We bind or provide the listener in form of function name or method name as a variable. |
| The string we pass to the listener should have “( )” at the end in order to work. | We are only suppose to pass the method  name and nothing else. React can determine that it has to run this method. |
| We can add event listener any time using external javascript. | We have to specify all the Events at the time of creating the component. |

- Binding methods or event handlers in JSX callbacks (Class components)
```a
There are 3 possible ways to achieve this:

1. Binding in Constructor: In JavaScript classes, the methods are not bound by default. The same thing applies for React event handlers defined as class methods. Normally we bind them in constructor.
```
```
class Component extends React.Component {
  constructor(props) {
    super(props);
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    // ...
  }
}
```
```a
2. Public class fields syntax: If you don't like to use bind approach then public class fields syntax can be used to correctly bind callbacks.
```
```
handleClick = () => {
  console.log('this is:', this);
};
```
```
<button onClick={this.handleClick}>{'Click me'}</button>
```
```a
3. Arrow functions in callbacks: You can use arrow functions directly in the callbacks.
```
```
<button onClick={(event) => this.handleClick(event)}>{'Click me'}</button>
```
> Note: If the callback is passed as prop to child components, those components might do an extra re-rendering. In those cases, it is preferred to go with .bind() or public class fields syntax approach considering performance.

- Arrow functions in render methods
```a
Arrows prevent "this" bugs:
Arrow functions don’t redefine the value of this within their function body. This makes it a lot easier to predict their behavior when passed as callbacks, and prevents bugs caused by use of this within callbacks

Here’s an example of the type of bug that arrow functions prevent. At first glance, you may expect the button’s background color to change to red when you click it. But if you actually click the button, you’ll find that nothing changes…
```

- Passing a parameter to an event handler or callback
```a
If you want to pass a parameter to the click event handler you need to make use of the arrow function or bind the function. If you pass the argument directly the onClick function would be called automatically even before pressing the button.
```

- Synthetic events in React
```a
Your event handlers will be passed instances of SyntheticEvent, a cross-browser wrapper around the browser’s native event. It has the same interface as the browser’s native event, including stopPropagation() and preventDefault(), except the events work identically across all browsers.

If you find that you need the underlying browser event for some reason, simply use the nativeEvent attribute to get it. The synthetic events are different from, and do not map directly to, the browser’s native events. For example in onMouseLeave event.nativeEvent will point to a mouseout event. The specific mapping is not part of the public API and may change at any time. 
```

### Rendering

- render() in React
```a
Class components uses render function. The ReactDOM.render() function takes two arguments, HTML code and an HTML element.

Purpose of render():
- React renders HTML to the web page by using a function called render().
- The purpose of the function is to display the specified HTML code inside the specified HTML element.
- In the render() method, we can read props and state and return our JSX code to the root component of our app.
- In the render() method, we cannot change the state, and we cannot cause side effects( such as making an HTTP request to the webserver).
```

- State update
```a
1. In Class components:
Use this.setState(object)

2. In Functional components:
Use useState() hook

When we put the new object/value to this methods, React try to find difference between previous and current object/value and if there is, it makes a rerender there.
```

- Conditional rendering
```a
In React, you can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application.

Conditional rendering in React works the same way conditions work in JavaScript. Use JavaScript operators like if or the conditional operator to create elements representing the current state, and let React update the UI to match them.
```
```
function UserGreeting(props) {
  return <h1>Welcome back!</h1>;
}

function GuestGreeting(props) {
  return <h1>Please sign up.</h1>;
}
```
```
function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;
  if (isLoggedIn) {
    return <UserGreeting />;
  }

  return <GuestGreeting />;
}

ReactDOM.render(
  // Try changing to isLoggedIn={true}:
  <Greeting isLoggedIn={false} />,
  document.getElementById('root')
);
```

- `key` prop: when to use it, using index as a key
```a
A “key” is a special string attribute you need to include when creating lists of elements in React. Keys are used to React to identify which items in the list are changed, updated, or deleted. In other words, we can say that keys are used to give an identity to the elements in the lists. The next thing that comes to mind is that what should be good to be chosen as key for the items in lists. It is recommended to use a string as a key that uniquely identifies the items in the list.

Using index as a key may break your application and display wrong data!

We might face following issues when we use index value as key attribute when creating a list:
- Performance Issues due to unnecessary re-renders.
- Issues in data mapping in case list items are sorted, filtered, or deleted.
```

- What is `children` prop?
```a
React provides a special prop that you can use to denote content between the start and ending tags.

In React, you can achieve the same using props.children:
```
```
<Button>
  <i>icon</i>
  <span>Content</span>
</Button>
```
```a
Inside Button component, you can access children as:
```
```
function Button({ children }) {
  return <button>{children}</button>
}
```

> Note that children as a prop does not need to be passed explicitly. React passes whatever content you have passed inside special children prop. Children is fit for passing in large values which can be substituted with any React element, React also provides a dedicated API for dealing with children.

- What are render props?
```a
The term “render prop” refers to a technique for sharing code between React components using a prop whose value is a function.

A component with a render prop takes a function that returns a React element and calls it instead of implementing its own render logic.

In a Class components:
```
```
class NameWrapper extends Component {
  state = { 
     name: 'Dan Abramov' 
  };
  render() {
    return this.props.render(this.state.name);
  }
}
const Name = () => (
  <NameWrapper render={name => <h2>Hi, {name}!</h2>} />
);
```
```a
In a Functional components:
```
```
const App = () => {
  return (
    <SomeParent>
      <SomeChild/>
    </SomeParent>
  );
}
```

- What are fragments?
```a
A common pattern in React is for a component to return multiple elements. Fragments let you group a list of children without adding extra nodes to the DOM.
```
```
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
```

### Refs

- What is the use of `refs`?
```a
Refs provide a way to access DOM nodes or React elements created in the render method.

There are a few good use cases for refs:
- Managing focus, text selection, or media playback.
- Triggering imperative animations.
- Integrating with third-party DOM libraries.

Let's say we want to programmatically focus an input element when the user clicks a button. React doesn't have a built-in way of doing this, but in plain JavaScript, we would query the DOM to find the element first and then call the focus function that's part of the element.
```
```
const inputElement = document.getElementById('input-element-id');
inputElement.focus();
```
```a
React makes these operations a bit easier by allowing us to store references to DOM elements like this:
```
```
const App = () => {
  const inputRef = useRef(null);

  return (
    <>
      <input
        ref={inputRef}
        value={name}
        onChange={handleChange}
      />
      <button
        onClick={() => inputRef.current.focus()}
      >
        Focus
      </button>
    </>
  );
};
```

- How to create `refs`?
```a
Refs are created using React.createRef() and attached to React elements via the ref attribute. Refs are commonly assigned to an instance property when a component is constructed so they can be referenced throughout the component.
```
```
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.myRef = React.createRef();
  }

  render() {
    return <div ref={this.myRef} />;
  }
}
```

- What are `forward refs`?
```a
Ref forwarding is a technique for automatically passing a ref through a component to one of its children. This is typically not necessary for most components in the application. However, it can be useful for some kinds of components, especially in reusable component libraries. The most common scenarios are described below.

Our task is to forward the ref that the Input component receives to the HTML input element.

We do that by wrapping the component in forwardRef. The function accepts a callback with two parameters:
- The component props
- The ref to be forwarded

This callback is our function component, which now accepts a second property.
```
```
const Input = forwardRef((props, ref) => {
  // Here goes the content of our component
});
```
```a
In the returned JSX code, we now need to pass the ref we receive in the function to the correct HTML component, which in our case is the input element.
```
```
const Input = forwardRef((props, ref) => {
  return (
    <input
      ref={ref}
      {...props}
    />
  );
});
```
```a
Et voilá, focussing the input via refs works!

Here's the code for doing so:
```
```
import React, { useState, useRef, forwardRef } from 'React';

const Input = forwardRef((props, ref) => {
  return <input ref={ref} {...props} />;
});

const App = () => {
  const inputRef = useRef(null);
  const [value, setValue] = useState('');
  const onInputChange = (e) => {
    e.preventDefault();
    setValue(e.target.value);
  };

  const focus = () => {
    inputRef.current?.focus();
  };

  return (
    <>
      <Input value={value} onChange={onInputChange} ref={inputRef} />
      <button onClick={focus}>Focus</button>
    </>
  );
};
```

### Hooks

- What are hooks?
```a
They let you use state and other React features without writing a class. Hooks are the functions which "hook into" React state and lifecycle features from function components. It does not work inside classes.
```

- Rules of Hooks
```a
Hooks are similar to JavaScript functions, but you need to follow these two rules when using them. Hooks rule ensures that all the stateful logic in a component is visible in its source code. These rules are:

1. Only call Hooks at the top level:
Do not call Hooks inside loops, conditions, or nested functions. Hooks should always be used at the top level of the React functions. This rule ensures that Hooks are called in the same order each time a components renders.

2. Only call Hooks from React functions:
You cannot call Hooks from regular JavaScript functions. Instead, you can call Hooks from React function components. Hooks can also be called from custom Hooks.
```

- `useState`, `useEffect`
```a
1. useState:
Hook state is the new way of declaring a state in React app. Hook uses useState() functional component for setting and retrieving state.

2. useEffect:
The Effect Hook allows us to perform side effects (an action) in the function components. It does not use components lifecycle methods which are available in class components. In other words, Effects Hooks are equivalent to componentDidMount(), componentDidUpdate(), and componentWillUnmount() lifecycle methods.

Side effects have common features which the most web applications need to perform, such as:
- Updating the DOM
- Fetching and consuming data from a server API
- Setting up a subscription, etc
```

### Component lifecycle

- What are the different phases of a component lifecycle?
```a
Each component in React has a lifecycle which you can monitor and manipulate during its three main phases.

The three phases are: Mounting, Updating, and Unmounting.

1. Mounting:
Mounting means putting elements into the DOM.

React has four built-in methods that gets called, in this order, when mounting a component:
- constructor()
- getDerivedStateFromProps()
- render()
- componentDidMount()

2. Updating
The next phase in the lifecycle is when a component is updated.

A component is updated whenever there is a change in the component's state or props.

React has five built-in methods that gets called, in this order, when a component is updated:
- getDerivedStateFromProps()
- shouldComponentUpdate()
- render()
- getSnapshotBeforeUpdate()
- componentDidUpdate()

3. Unmounting
The next phase in the lifecycle is when a component is removed from the DOM, or unmounting as React likes to call it.

React has only one built-in method that gets called when a component is unmounted:
- componentWillUnmount()
```

- What are the lifecycle methods of React? (Before v16.3 vs. After v16.3 vs. After v16.8)

| Before v16.3 | After v16.3 | After v16.8 |
| ------------ | ----------- | ----------- |
| `componentWillMount()` | `componentDidMount` | `useEffect()` |
| `componentDidMount()` | `getDerivedStateFromProps()` | |
| `componentWillReceiveProps()` | `shouldComponentUpdate()` | |
| `shouldComponentUpdate()` | `getSnapshotBeforeUpdate()` | |
| `componentWillUpdate()` | `componentDidUpdate()` | |
| `componentDidUpdate()` | `componentWillUnmount` | |
| `componentWillUnmount()` | | |


### Styling

- Styled components
```a
In React’s own words, styled components are “visual primitives for components”, and their goal is to give us a flexible way to style components. The result is a tight coupling between components and their styles.
```
```
import styled from "styled-components";

// Styled component named StyledButton
const StyledButton = styled.button`
  background-color: black;
  font-size: 32px;
  color: white;
`;

function Component() {
  // Use it like any other component.
  return <StyledButton> Login </StyledButton>;
}
```

- CSS Modules
```a
CSS Modules let you use the same CSS class name in different files without worrying about naming clashes.
```
```
import React, { Component } from 'react';
import styles from './Button.module.css'; // Import css modules stylesheet as styles
import './another-stylesheet.css'; // Import regular stylesheet

class Button extends Component {
  render() {
    // reference as a js object
    return <button className={styles.error}>Error Button</button>;
  }
}
```

### HTTP interaction

- `fetch` vs. `axios`

| fetch | axios |
| ----- | ----- |
| Fetch has no url in request object. | Axios has url in request object. |
| Fetch is built into most modern browsers; no installation is required as such. | Axios is a stand-alone third party package that can be easily installed. |
| Fetch does not. | Axios enjoys built-in XSRF protection. |
| Fetch uses the body property. | Axios uses the data property. |
| Fetch’s body has to be stringified. | Axios’ data contains the object. |
| Fetch request is ok when response object contains the ok property. | Axios request is ok when status is 200 and statusText is ‘OK’. |
| Fetch is a two-step process when handling JSON data- first, to make the actual request; second, to call the .json() method on the response. | Axios performs automatic transforms of JSON data. |
| Fetch does not. | Axios allows cancelling request and request timeout. |
| Fetch, by default, doesn’t provide a way to intercept requests. | Axios has the ability to intercept HTTP requests. |
| Fetch does not support upload progress. | Axios has built-in support for download progress. |
| Fetch only supports Chrome 42+, Firefox 39+, Edge 14+, and Safari 10.1+ (This is known as Backward Compatibility). | Axios has wide browser support. |

- Does React have interceptors?
```a
Interceptors are a feature that allows an application to intercept requests or responses before they are handled by the .then() or the .catch()

Axios interceptors are the default configurations that are added automatically to every request or response that a user receives. It is useful to check response status code for every response that is being received.
```

- Wrapper of http client
```a
This wrapper is supposed to provide a clean interface for setting various parameters in your request (query params, body, content type etc.) and handle various redundant tasks like the marshalling/unmarshalling of request/response, closing response body after it has been read etc.

All you need is the request struct, endpoint, authentication params etc at your disposal and rest of the work can be taken care of with just a few lines of code thereby preventing code duplication and at the same easing the developer of redundant efforts involved in such cases.
```

### React Router

- What is React router?
```a
React Router is a standard library for routing in React. It enables the navigation among views of various components in a React Application, allows changing the browser URL, and keeps the UI in sync with the URL.
```

- How React Router is different from history library?
```a
React Router is a wrapper around the history library which handles interaction with the browser's window.history with its browser and hash histories. It also provides memory history which is useful for environments that don't have global history, such as mobile app development (React Native) and unit testing with Node.
```

- What are the `<Router>` components?
```a
There are three primary categories of components in React Router:
- routers, like <BrowserRouter> and <HashRouter>
- route matchers, like <Route> and <Switch>
- and navigation, like <Link>, <NavLink>, and <Redirect>

We also like to think of the navigation components as “route changers”.

All of the components that you use in a web application should be imported from react-router-dom.

Routers:
At the core of every React Router application should be a router component. For web projects, react-router-dom provides <BrowserRouter> and <HashRouter> routers. The main difference between the two is the way they store the URL and communicate with your web server.
- A <BrowserRouter> uses regular URL paths. These are generally the best-looking URLs, but they require your server to be configured correctly. Specifically, your web server needs to serve the same page at all URLs that are managed client-side by React Router. Create React App supports this out of the box in development, and comes with instructions on how to configure your production server as well.
- A <HashRouter> stores the current location in the hash portion of the URL, so the URL looks something like http://example.com/#/your/page. Since the hash is never sent to the server, this means that no special server configuration is needed.

To use a router, just make sure it is rendered at the root of your element hierarchy. Typically you’ll wrap your top-level <App> element in a router, like this:
```

- How to programmatically navigate using React Router?
```a
1. Using Redirect Component:
The primary way you programmatically navigate using React Router v4+ is by using a <Redirect /> component, and it’s a recommended method that helps the user navigate between routes.

Using the Redirect component is a different approach but just as valid. The idea is to have it pointing at a state in the component, and if that condition is fulfilled, then navigate.

Some might argue that this method requires more work as one needs to create a new prop on the component’s state and add a condition to the render method to check when to render the Redirect component. This is a fact, but a counter and valid argument, from those who prefer explicit to implicit: It points to the idea that explicitly defining and modifying your state is better as it makes the code more readable against the implicit state handled by an imperative API such as history.push, which we will go over in a bit.

2. Using history.push() Method:
history.push() is another approach where we make use of the history props React Router provides while rendering a component.

In other words, this works when the component is being rendered by React Router, bypassing the component as a Component prop to a Route. If this is the case, the React Router exposes three props to the component: location, match and history.

3. Using withRouter Method:
We mentioned earlier that for a component to have access props.history.push it must have been rendered with React Router. There are cases where this might not be the case. Thus, we render a component ourselves. To make the history property available to the component, the React Router team created the Higher Order Component (HOC) withRouter. Wrapping a component with this HOC exposes the properties as well.

4. Using useHistory Hook:
As of recent versions of React Router (v5.1) and React (v16.8), we have a new method called the useHistory hook which embraces the power of React Hooks. This is used for programmatic navigation purposes within a functional component. The useHistory hook gives you access to the history instance that we can use to navigate between pages, whether the component has been rendered by React Router or not, and this eliminates the need for using withRouter.
```

- Route guard
```a
Whenever you develop a React-Application there will be the need to restrict unauthenticated users to access certain parts of your application.
React Router is my library of choice when it comes to routing for React, but there is no built-in way to protect a <Route> from unrestricted access. In this post I will show you how to easily build your own guarded routes.

Now we want to guard the protected page from unrestricted user access.
We need to write a GuardedRoute which wraps a normal React-Router <Route>:
```
```
import React from 'react';
import { Route, Redirect } from "react-router-dom";

const GuardedRoute = ({ component: Component, auth, ...rest }) => (
    <Route {...rest} render={(props) => (
        auth === true
            ? <Component {...props} />
            : <Redirect to='/' />
    )} />
)

export default GuardedRoute;
```

- How to get query parameters in React Router?
```a
1. Get a single Query String value:
Reading from the URL and getting your query string with React Router v6 is relatively simple but takes a few steps, and then you need to decide whether you want a single query string parameter or all of them at once.

First you’ll need to import the useSearchParams hook and destruct the return value to get the current value of, React Router v6 calls these the “search params” due to them existing on the window.location.search object:
```
```
import React from 'react';
import { useSearchParams } from 'react-router-dom';

const Users = () => {
  const [searchParams] = useSearchParams();
  console.log(searchParams); // ▶ URLSearchParams {}

  return <div>Users</div>;
};
```
```a
2. Get all Query String values as an object:
Next up is how to get all the parameters from the query string URLSearchParams object. Thankfully we have an .entries() method to use, however it doesn’t quite work out of the box if we want a straight up object to use, see below how it logs out Iterator {}:
```
```
const Users = () => {
  const [searchParams] = useSearchParams();
  console.log(searchParams.entries()); // ▶ Iterator {}

  return <div>Users</div>;
};
```

### Code quality

- Common folder structures in React
```a
1. Assets Folder:
As the name says, it contains assets of our project. It consists of images and styling files. Here we can store our global styles. We are centralizing the project so we can store the page-based or component-based styles over here. But we can even keep style according to the pages folder or component folder also. But that depends on developer comfortability.

2. Layouts Folder:
As the name says, it contains layouts available to the whole project like header, footer, etc. We can store the header, footer, or sidebar code here and call it.

3. Components Folder:
Components are the building blocks of any react project. This folder consists of a collection of UI components like buttons, modals, inputs, loader, etc., that can be used across various files in the project. Each component should consist of a test file to do a unit test as it will be widely used in the project.

4. Pages Folder:
The files in the pages folder indicate the route of the react application. Each file in this folder contains its route. A page can contain its subfolder. Each page has its state and is usually used to call an async operation. It usually consists of various components grouped.

5. Middleware Folder:
This folder consists of middleware that allows for side effects in the application. It is used when we are using redux with react. Here we keep all our custom middleware.

6. Routes Folder:
This folder consists of all routes of the application. It consists of private, protected, and all types of routes. Here we can even call our sub-route.

7. Config Folder:
This folder consists of a configuration file where we store environment variables in config.js. We will use this file to set up multi-environment configurations in your application.

8. Services Folder:
This folder will be added if we use redux in your project. Inside it, there are 3 folders named actions, reducers, and constant subfolders to manage states. The actions and reducers will be called in almost all the pages, so create actions, reducers & constants according to pages name.

9. Utils Folder:
Utils folder consists of some repeatedly used functions that are commonly used in the project. It should contain only common js functions & objects like dropdown options, regex condition, data formatting, etc.

10. Final Project Structure:
So our final architecture of the react project is complete, and it looks something like this. You can customize this according to your requirements.
```

- What are PropTypes? Difference with TypeScript?
```a
Both of these tools are used for type-checking props. Although TypeScript may seem like the best option now, choosing one will inevitably result in a trade-off. Here are some key differences to consider:

1. Runtime and compile time type checking
PropTypes does type-checking during runtime while the application is running in the browser. However, TypeScript does type-checking during compile time when the TypeScript code is compiled to JavaScript. This is worth noting because it influences how the tools can be used.

2. Syntax and semantic highlighting
Both tools have plugins that provide autocompletion with information on components’ props. However, TypeScript’s highlighting tools outperform PropTypes’. You’ll find numerous features in TypeScript IDE tools like VS Code, WebStorm, and Atom. TypeScript highlights your components appropriately when the expected props’ data types are not provided and provides insights into the solution.

3. Advanced features in TypeScript
There are many ways you can specify types for your props in TypeScript that PropTypes may not be able to provide. For example, TypeScript allows you to combine interfaces with types and perform conditional type checking, like stating that if property A is true, property C must also be provided.
```

- React-specific linters?
```a
ESLint is a popular JavaScript linter. There are plugins available that analyse specific code styles. One of the most common for React is an npm package called eslint-plugin-react. By default, it will check a number of best practices, with rules checking things from keys in iterators to a complete set of prop types.

Another popular plugin is eslint-plugin-jsx-a11y, which will help fix common issues with accessibility. As JSX offers slightly different syntax to regular HTML, issues with alt text and tabindex, for example, will not be picked up by regular plugins.
```

### Context

- What is `Context`?
```a
Context provides a way to pass data through the component tree without having to pass props down manually at every level.

In a typical React application, data is passed top-down (parent to child) via props, but such usage can be cumbersome for certain types of props (e.g. locale preference, UI theme) that are required by many components within an application. Context provides a way to share values like these between components without having to explicitly pass a prop through every level of the tree.

When to Use Context
Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language. For example, in the code below we manually thread through a “theme” prop in order to style the Button component:
```
```
class App extends React.Component {
  render() {
    return <Toolbar theme="dark" />;
  }
}

function Toolbar(props) {
  // The Toolbar component must take an extra "theme" prop
  // and pass it to the ThemedButton. This can become painful
  // if every single button in the app needs to know the theme
  // because it would have to be passed through all components.
  return (
    <div>
      <ThemedButton theme={props.theme} />
    </div>
  );
}

class ThemedButton extends React.Component {
  render() {
    return <Button theme={this.props.theme} />;
  }
}
```
```a
Using context, we can avoid passing props through intermediate elements:
```
```
// Context lets us pass a value deep into the component tree
// without explicitly threading it through every component.
// Create a context for the current theme (with "light" as the default).
const ThemeContext = React.createContext('light');

class App extends React.Component {
  render() {
    // Use a Provider to pass the current theme to the tree below.
    // Any component can read it, no matter how deep it is.
    // In this example, we're passing "dark" as the current value.
    return (
      <ThemeContext.Provider value="dark">
        <Toolbar />
      </ThemeContext.Provider>
    );
  }
}

// A component in the middle doesn't have to
// pass the theme down explicitly anymore.
function Toolbar() {
  return (
    <div>
      <ThemedButton />
    </div>
  );
}

class ThemedButton extends React.Component {
  // Assign a contextType to read the current theme context.
  // React will find the closest theme Provider above and use its value.
  // In this example, the current theme is "dark".
  static contextType = ThemeContext;
  render() {
    return <Button theme={this.context} />;
  }
}
```

- Explain createContext/Provider/contextType/Consumer/displayName
```a
1. React.createContext:
const MyContext = React.createContext(defaultValue);
Creates a Context object. When React renders a component that subscribes to this Context object it will read the current context value from the closest matching Provider above it in the tree.

The defaultValue argument is only used when a component does not have a matching Provider above it in the tree. This default value can be helpful for testing components in isolation without wrapping them. Note: passing undefined as a Provider value does not cause consuming components to use defaultValue.

2. Context.Provider:
```
```
<MyContext.Provider value={/* some value */}>
```
```a
Every Context object comes with a Provider React component that allows consuming components to subscribe to context changes.

The Provider component accepts a value prop to be passed to consuming components that are descendants of this Provider. One Provider can be connected to many consumers. Providers can be nested to override values deeper within the tree.

All consumers that are descendants of a Provider will re-render whenever the Provider’s value prop changes. The propagation from Provider to its descendant consumers (including .contextType and useContext) is not subject to the shouldComponentUpdate method, so the consumer is updated even when an ancestor component skips an update.

Changes are determined by comparing the new and old values using the same algorithm as Object.is.

3. Class.contextType:
```
```
class MyClass extends React.Component {
  componentDidMount() {
    let value = this.context;
    /* perform a side-effect at mount using the value of MyContext */
  }
  componentDidUpdate() {
    let value = this.context;
    /* ... */
  }
  componentWillUnmount() {
    let value = this.context;
    /* ... */
  }
  render() {
    let value = this.context;
    /* render something based on the value of MyContext */
  }
}
```
```a
MyClass.contextType = MyContext;
The contextType property on a class can be assigned a Context object created by React.createContext(). Using this property lets you consume the nearest current value of that Context type using this.context. You can reference this in any of the lifecycle methods including the render function.

4. Context.Consumer:
```
```
<MyContext.Consumer>
  {value => /* render something based on the context value */}
</MyContext.Consumer>
```
```a
A React component that subscribes to context changes. Using this component lets you subscribe to a context within a function component.

Requires a function as a child. The function receives the current context value and returns a React node. The value argument passed to the function will be equal to the value prop of the closest Provider for this context above in the tree. If there is no Provider for this context above, the value argument will be equal to the defaultValue that was passed to createContext().

5. Context.displayName
Context object accepts a displayName string property. React DevTools uses this string to determine what to display for the context.

For example, the following component will appear as MyDisplayName in the DevTools:
```
```
const MyContext = React.createContext(/* some value */);
MyContext.displayName = 'MyDisplayName';

<MyContext.Provider> // "MyDisplayName.Provider" in DevTools
<MyContext.Consumer> // "MyDisplayName.Consumer" in DevTools
```

- Pros and Cons of `Context`

| Pros | Cons |
| ---- | ---- |
| The build-in React tool has not influenced the final bundle size, and it is integrated by design with every npm package | Context-API is not designed for often refreshed or changed data |
| Easier to understand and handle for beginners comparing to Redux data flow | There could be more difficult maintenance in more complex frontend applications, especially if we have custom solutions and helpers |
| Excellent for more static data - not so frequency updated like in Redux | Reuse components are harder, because some data come from context, not always from props |
| Only little setup is required - create context and sometimes wrapper component | |
| Well documented part of React | |
| A lot of local contexts to handle separate logic tasks can be in the application | |

### Redux

- What is Redux?
```a
Redux is a predictable state container for JavaScript apps.

It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test. On top of that, it provides a great developer experience, such as live code editing combined with a time traveling debugger.

You can use Redux together with React, or with any other view library. It is tiny (2kB, including dependencies), but has a large ecosystem of addons available.

There are three principles of Redux:
- Single source of truth
- State is read-only
- Changes are made with pure functions
```

- How is Redux working? What are the components in Redux?
```a
1. How is Redux working?
In short, Redux gives you a single object that holds the state for your entire application in one location — that could include data from your backend API or an external API, state for navigation, a user’s information, toggled state of a button, and so on.
This is powerful because it allows easier scalability and the ability to quickly diagnose bottlenecks, asynchronous issues, or errors.

The way Redux works is simple. There is a central store that holds the entire state of the application. Each component can access the stored state without having to send down props from one component to another.

2. What are the components in Redux?
There are three building parts: store, reducers and actions.

Store:
The store is an object that holds the application state. It is highly recommended to keep only one store in any Redux application. You can access the state stored, update the state, and register or unregister listeners via helper methods.

Reducers:
A Reducer is a pure function that takes the state of an application and action as arguments and returns a new state. For example, an authentication reducer can take an initial state of an application in form of an empty object and an action that tells it that a user has logged in and returned a new application state with a logged-in user.

Pure functions are functions that do not have any side effects and will return the same results if the same arguments are passed in.
```
```
const initialState = {};
const cartReducer = (state = initialState, action) => {
  // Do something here
}
```
```a
Actions:
An action, is an object that contains the payload of information. They are the only source of information for the Redux store to be updated. Reducers update store based on the value of the action.type. Here we will define the action.type as ADD_TO_CART.

According to the official Redux documentation, actions are the only things that trigger changes in a Redux application, they contain the payload for changes to an application store. Actions are JavaScript objects that tell Redux the type of action to be performed, usually they’re defined as functions like the one below:
```
```
const action = {
  type: 'ADD_TO_CART',
  payload: {
    product: 'margarine',
    quantity: 4
  }
}
```

- When to use Redux?
```a
Redux is most useful when in cases when:
- You have large amounts of application state that are needed in many places in the app
- The app state is updated frequently
- The logic to update that state may be complex
- The app has a medium or large-sized codebase, and might be worked on by many people
- You need to see how that state is being updated over time
```

- React state vs. Redux vs. Context
```a
State #
The React state is the data that your component(s) is working with — it holds the data that a component requires and it dictates what a component renders. Once a state object changes, the component re-renders. If an application state is managed by Redux, then the reducer is where state changes happen.
```

| Redux | Context |
| ----- | ------- |
| Additional installation Required, driving up the final bundle size | Built-in tool that ships with React |
| Requires extensive setup to integrate it with a React Application | Requires minimal Setup |
| Works like a charm with both static and dynamic data | Specifically designed for static data, that is not often refreshed or updated |
| Easily extendible due to the ease of adding new data/actions after the initial setup | Adding new contexts requires creation from scratch |
| Incredibly powerful Redux Dev Tools to ease debugging | Debugging can be hard in highly nested React Component Structure even with Dev Tool |
| Better code organization with separate UI logic and State Management Logic | UI logic and State Management Logic are in the same component |

- How to add multiple middlewares to Redux?
```a
Middleware is the suggested way to extend Redux with custom functionality. Middleware lets you wrap the store's dispatch method for fun and profit. The key feature of middleware is that it is composable. Multiple middleware can be combined together, where each middleware requires no knowledge of what comes before or after it in the chain.
```
```
const store = createStore(reducers, applyMiddleware(ReduxThunk, logger));

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.querySelector('#app')
);
```

- What are Redux DevTools?
```a
Redux DevTools for debugging application's state changes.
The extension provides power-ups for your Redux development workflow. Apart from Redux, it can be used with any other architectures which handle the state.
```


## Advanced


### Virtual DOM
- What is React Fiber?
```a
React Fiber is a backwards compatible, complete rewrite of the React core. In other words, it is a reimplementation of older versions of the React reconciler.

Introduced from React 16, Fiber Reconciler is the new reconciliation algorithm in React. The term Fiber refers to React's data structure (or) architecture, and originates from 'fiber' - a representation of a node of the DOM tree.

1. What is the purpose of React Fiber?
1.1. Improved performance:
- React Fiber is aimed at improving the perceived performance for complex React applications. It does so by allowing React to break the limits of the call stack. This lets it pause or start rendering work whenever required.

1.2. Better suitability for advanced UI.
- React Fiber also increases the suitability of the React library to create animations, layouts, and gestures.

1.3. Control over the "priority" of work
- Through its feature of incremental rendering, React Fiber lets developers split rendering work into smaller chunks and distribute it over multiple frames. This allows users to essentially control the "priority" of work.
- For example, React Fiber could help you prioritise functions that originate from user actions while delaying logic of less-important background or offscreen functions to avoid frame rate drops.

1.4. More fluid experience
- So by breaking up the work into smaller chunks that can be paused, resumed, or aborted based on a set priority order, React Fiber helps apps deliver a more fluid experience. Fiber lets React fine-tune the rendering to ensure that the most common use-cases (or) the most important updates are computed at the earliest.
- Specifically, it helps improve the speed of rendering components at start-up, as they could be made available to the browser before the entire bundle finishes downloading.

2. What are the features of React Fiber?
React Fiber brings in a host of new capabilities, such as:
- Supporting better error handling and recovering from errors
- Rendering subtrees into DOM node containers (Portals)
- Support for new render return types like fragments and strings
- Returning multiple elements from a render function

3. How does React Fiber work?
Fiber brings in different levels of priority for updates in React. It breaks the computation of the component tree into nodes, or 'units' of work that it can commit at any time. This allows React to pause, resume or restart computation for various components.

Fiber allows the reconciliation and rendering to the DOM to be split into two separate phases:

3.1. Phase 1: Reconciliation
- In the first phase, React creates a list of all changes to be rendered in the UI (an 'effect list', comprising of new and updated components).
- Once the list is fully computed, React will schedule these changes to be executed in the next phase.
- Note that React doesn't make any actual changes in this phase.

3.2. Phase 2: Commit
- In phase two, also called 'commit' phase, React tells the DOM to render the effect list that was created in the previous phase.
- While the Reconciliation phase can be interrupted, the Commit phase cannot.
- So via Fiber, React is able to traverse the component tree through a singly linked list tree traversal algorithm. This algorithm can run in an "asynchronous" manner - allowing React to pause and resume work at particular nodes.
```

### Hooks

- Custom hook with examples
```a
Hooks are reusable functions.

When you have component logic that needs to be used by multiple components, we can extract that logic to a custom Hook.

Custom Hooks start with "use". Example: "useFetch".
```
```
import { useState, useEffect } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((data) => setData(data));
  }, [url]);

  return [data];
};

export default useFetch;
```

### React Router

- How to pass params to `history.push` method in React Router?
```a
According to the docs:
- length – (number) The number of entries in the history stack.
- action – (string) The current action (PUSH, REPLACE, or POP)
- location – (object) The current location.
- push(path, [state]) – (function) Pushes a new entry onto the history stack.

What is history PUSH IN react router?
- You can get access to the history object’s properties and the closest‘s match via the "withRouter" higher-order component. "withRouter" will re-render its component every time the route changes with the same props as render props: { match, location, history } .
```

### Redux

- What is `redux-thunk`?
```a
Redux Thunk is middleware that allows you to return functions, rather than just actions, within Redux. This allows for delayed actions, including working with promises.

One of the main use cases for this middleware is for handling actions that might not be synchronous, for example, using axios to send a GET request. Redux Thunk allows us to dispatch those actions asynchronously and resolve each promise that gets returned.

How to Use Redux Thunk:
- Once Redux Thunk has been installed and included in your project with applyMiddleware(thunk), you can start dispatching actions asynchronously.

For example, here's a simple increment counter:
```
```
const INCREMENT_COUNTER = 'INCREMENT_COUNTER';

function increment() {
  return {
    type: INCREMENT_COUNTER
  };
}

function incrementAsync() {
  return dispatch => {
    setTimeout(() => {
      // You can invoke sync or async actions with `dispatch`
      dispatch(increment());
    }, 1000);
  };
}
```
```a
And here's how set up success and failure actions after polling an API:
```
```
const GET_CURRENT_USER = 'GET_CURRENT_USER';
const GET_CURRENT_USER_SUCCESS = 'GET_CURRENT_USER_SUCCESS';
const GET_CURRENT_USER_FAILURE = 'GET_CURRENT_USER_FAILURE';

const getUser = () => {
  return (dispatch) => {  //nameless functions
    // Initial action dispatched
    dispatch({ type: GET_CURRENT_USER });
    // Return promise with success and failure actions
    return axios.get('/api/auth/user').then(  
      user => dispatch({ type: GET_CURRENT_USER_SUCCESS, user }),
      err => dispatch({ type: GET_CURRENT_USER_FAILURE, err })
    );
  };
};
```

- Design patterns
```a
1. Rails-style:
The Rails-style convention of code structure suggests that code should be separated into files within function-specific folders such as Components, Actions, Reducers, Middleware, etc. The resulting folder structure resembles the way in which many Rails projects are organized into function-specific folders for Models, Views, and Controllers. This design pattern suffices for smaller projects, but as apps grow, each of these folders can quickly become unwieldy. Each folder could contain dozens, potentially even hundreds, of files which becomes very difficult to manage.

2. Domain-style:
A domain-style design pattern helps to address the issue of bloated, unmanageable, Rails-style folders by organizing files into folders based on app features such as User, Post, Order, etc. All files regarding Orders, for example, would be located within the Order folder, and that folder would then contain files for Order related components, actions, reducers, and helper functions. This file structure allows for quick access to relevant files when working on specific app features, and eliminates the need to search through large, cluttered folders and files.

3. Ducks pattern:
While the domain-centric pattern is a big step in the right direction, our dev team at SmartLogic has found the Ducks pattern to be an even more effective way to organize our code. As in the domain-style convention, code is organized based on features of the app. The "ducks" pattern, however, combines the actions, action type constants, and reducers into a single redux file.

This consolidation of Redux-specific code leads to leaner project directories which has proved to be very beneficial as our apps grow. Additionally, when working on redux-related code, less files need to be touched. These benefits normally come at a cost, though. Combining actions, action type constants, and reducer logic could potentially result in very large redux files.
```
```a
Reduxsauce:
Reduxsauce is a library that provides concise methods for writing action creators and reducers. These methods allow action types to be mapped explicitly to reducers, and this removes the need to implement a switch-case statement. The reducer logic can then be defined separately from this mapping. As a result, the consolidated redux code becomes highly readable, and much easier to maintain and build upon. Additionally, each reducer function can be exported and thus more easily tested. In the end, all the benefits of the "ducks" design pattern can be maintained, while the lines of code required can be significantly reduced.
```

### Bundlers and transpilers

- What is Babel?
```a
Babel is a JavaScript compiler.

Babel is a toolchain that is mainly used to convert ECMAScript 2015+ code into a backwards compatible version of JavaScript in current and older browsers or environments. Here are the main things Babel can do for you:
- Transform syntax
- Polyfill features that are missing in your target environment (through a third-party polyfill such as core-js)
- Source code transformations (codemods)
```

- What is Webpack?
```a
At its core, webpack is a static module bundler for modern JavaScript applications — it takes all the code from your application and makes it usable in a web browser. Modules are reusable chunks of code built from your app's JavaScript, node_modules, images, and the CSS styles which are packaged to be easily used in your website.
```

- Name some benefits of using Webpack
```a
Webpack and static assets in a dependency graph offers many benefits. Here's a few:
- Dead asset elimination. This is killer, especially for CSS rules. You only build the images and CSS into your dist/ folder that your application actually needs.
- Easier code splitting. For example, because you know that your file Homepage.js only requires specific CSS files, Webpack could easily build a homepage.css file to greatly reduce initial file size.
- You control how assets are processed. If an image is below a certain size, you could base64 encode it directly into your Javascript for fewer HTTP requests. If a JSON file is too big, you can load it from a URL. You can require('./style.less') and it's automaticaly parsed by Less into vanilla CSS.
- Stable production deploys. You can't accidentally deploy code with images missing, or outdated styles.
- Webpack will slow you down at the start, but give you great speed benefits when used correctly. You get hot page reloading. True CSS management. CDN cache busting because Webpack automatically changes file names to hashes of the file contents, etc

Webpack is the main build tool adopted by the React community.
```

- Why and when should I use Webpack?
```a
If you're building a complex Front End application with many non-code static assets such as CSS, images, fonts, etc, then yes, Webpack will give you great benefits.

If your application is fairly small, and you don't have many static assets and you only need to build one Javascript file to serve to the client, then Webpack might be more overhead than you need.
```

### React testing

- What is Shallow Renderer in React testing?
```a
When writing unit tests for React, shallow rendering can be helpful. Shallow rendering lets you render a component “one level deep” and assert facts about what its render method returns, without worrying about the behavior of child components, which are not instantiated or rendered. This does not require a DOM.

For example, if you have the following component:
```
```
function MyComponent() {
  return (
    <div>
      <span className="heading">Title</span>
      <Subcomponent foo="bar" />
    </div>
  );
}
```
```a
Then you can assert:
```
```
import ShallowRenderer from 'react-test-renderer/shallow';

// in your test:
const renderer = new ShallowRenderer();
renderer.render(<MyComponent />);
const result = renderer.getRenderOutput();

expect(result.type).toBe('div');
expect(result.props.children).toEqual([
  <span className="heading">Title</span>,
  <Subcomponent foo="bar" />
]);
```
```a
Shallow testing currently has some limitations, namely not supporting refs.
```

- What is Jest?
```a
Jest is an open-source testing framework built on JavaScript, designed majorly to work with React and React Native based web applications. Often, unit tests are not very useful when run on the frontend of any software. This is mostly because unit tests for the front-end require extensive, time-consuming configuration. This complexity can be reduced to a great extent with the Jest framework.
Moreover, Jest can be used to validate almost everything around JavaScript, especially the browser rendering of web-applications. Jest is also widely preferred for automated browser testing, making it one of the most popular Javascript testing frameworks in existence.

Additionally, Jest provides a blended package of an assertion library along with a test runner and a built-in mocking library. It stands out by virtue of its simplicity, which makes it an ideal tool to test JavaScript Library Projects such as AngularJS, Vue JS, Node JS, Babel and TypeScript.
```
```a
Why Use Jest Framework For Selenium JavaScript Testing?
- Speed and Performance – Jest framework is fast when executing test cases
- Pre-commit hooks – Jest framework offers pre-commit hooks that execute sets of test cases that are significant in the current run or ones that have been changed after the previous commit
- Easy to Migrate – Any current test project can be migrated and switched to use the Jest framework programmatically without any issue or code interaction, thanks to the code mods module.
- Addition of Features and Configurations – The framework is not just an ordinary and basic test runner but also offers some advanced features. These include the ability to auto mock modules, setup coverage thresholds, module mappers. It also includes support from multiple projects in the same runner and customer resolvers such as Babel and Webpack.
```

- Name some of the advantages of Jest over Jasmine?
```a
- Automatically finds tests to execute in your source code.
- Automatically mocks dependencies when running your tests.
- Allows you to test asynchronous code synchronously.
- Runs your tests with a fake DOM implementation (via jsdom) so that your tests can be run on the command line.
- Runs tests in parallel processes so that they finish sooner.
```