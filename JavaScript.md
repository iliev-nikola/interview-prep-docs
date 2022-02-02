# JavaScript topics

Source: 
- https://www.javascripttutorial.net/
- https://www.w3schools.com/js/default.asp
- https://developer.mozilla.org/en-US/docs/Web/JavaScript 
- https://www.codecademy.com/learn/introduction-to-javascript
- https://www.patterns.dev/posts/classic-design-patterns/

## Basics

### JavaScript

- Getting started: What is JavaScript?
```a
JavaScript is a programming language initially designed to interact with elements of web pages. In web browsers, JavaScript consists of three main parts:
- ECMAScript provides the core functionality.
- The Document Object Model (DOM) provides interfaces for interacting with elements on web pages
- The Browser Object Model (BOM) provides the browser API for interacting with the web browser.

JavaScript allows you to add interactivity to a web page. Typically, you use JavaScript with HTML and CSS to enhance a web page’s functionality, such as validating forms, creating interactive maps, and displaying animated charts.
```

- Fundamentals: Syntax, Variables & Data types
```a
JavaScript has the primitive data types:
- null
- undefined
- boolean
- number
- string
- symbol – available from ES2015
- bigint – available from ES2020

and a complex data type:
- object
```

```a
- The undefined type is a primitive type that has only one value undefined. By default, when a variable is declared but not initialized, it is assigned the value of undefined.

- The null type is the second primitive data type that also has only one value null
```

```a
When you declare variables, the JavaScript engine allocates the memory for them on two memory locations: stack and heap.

Static data is the data whose size is fixed at compile time. Static data includes:
- Primitive values (null, undefined, boolean, number, string, symbol, and BigInt)
- Reference values that refer to objects.
Because static data has a size that does not change, the JavaScript engine allocates a fixed amount of memory space to the static data and store it on the stack.
```

```a
Unlike the stack, JavaScript stores objects (and functions) on the heap. The JavaScript engine doesn’t allocate a fixed amount of memory for these objects. Instead, it’ll allocate more space as needed.
```

- Operators
```a
- Arithmetic Operators: + - * /
- Remainder Operator: %
- Assignment Operators: = += -= *= /= %= &= |= ^= <<= >>= >>>=
- Unary Operators: +x -x ++x -x x++ x-
- Comparison Operators: < > <= >= == === !=
- Logical Operators: ! || &&
- Logical Assignment Operators: ||= &&= ??=
- Nullish Coalescing Operator: ??
- Exponentiation Operator: **
```

- Control flow Statements
```a
- if
- if else
- if else if
- Ternary Operator (:?)
- switch case
- while
- do while
- for
- break
- continue
- Comma Operator
```

- Functions: Function types, Function declaration & expression, Parameters & Arguments
```a
- A JavaScript function is a block of code designed to perform a particular task.

Function types:
- Function declaration
- Function expression
- Arrow function

Function declaration vs. expression:
- Function declaration: function myFunc() {} - have hoisting
- Function expression: let myFunc = function() {} - doesn't have hoisting

Function parameters vs. arguments:
- When declaring a function, you specify the parameters. However, when calling a function, you pass the arguments that are corresponding to the parameters.
```

- Objects & Prototypes
```a
this keyword:
- In general, the this references the object of which the function is a property. In other words, the this references the object that is currently calling the function.

for-in loop:
- The for...in  allows you to access each property and value of an object without knowing the specific name of the property.

Data properties:
A data property contains a single location for a data value. A data property has four attributes:
- Configurarable – determines whether a property can be redefined or removed via delete operator.
- Enumerable – indicates if a property can be returned in the for...in loop.
- Writable – specifies that the value of a property can be changed.
- Value – contains the actual value of a property.

Factory function:
- A factory function is a function that returns a new object: function createPerson(firstName, lastName) {};

Prototypes:
- Prototypes are the mechanism by which JavaScript objects inherit features from one another.
```

- Advanced Functions: Closure, IIFE, Arrow function, call/apply/bind, HOF, Callback, Pure function
```a
Closure:
- In JavaScript, a closure is a function that references variables in the outer scope from its inner scope. The closure preserves the outer scope inside its inner scope.

IIFE:
- A JavaScript immediately invoked function expression is a function defined as an expression and executed immediately after creation.

Arrow function:
- ES6 arrow functions provide you with an alternative way to write a shorter syntax compared to the function expression.
- In the arrow function, the "this", "arguments", "super", "new.target" are lexical. It means that the arrow function uses these variables (or constructs) from the enclosing lexical scope.
- An arrow function cannot be used as a function constructor. If you use the new keyword to create a new object from an arrow function, you will get an error.
- An arrow function doesn't have hoisting

When you should not use arrow functions:
- Event handlers
- Object methods
- Prototype methods
- Functions that use the arguments object

call, apply & bind:
- The apply() and call() methods call a function with a given this value and arguments.
- The bind() method creates a new function instance whose this value is bound to the object that you provide.

HOF:
- In Javascript, functions can be assigned to variables in the same way that strings or arrays can. They can be passed into other functions as parameters or returned from them as well.

A “higher-order function” is a function that accepts functions as parameters and/or returns a function:
.forEach()
.reduce()
.filter()
.sort()
.map()
etc...

Callback:
- By definition, a callback is a function that you pass into another function as an argument for executing later.

Pure function:
- Pure Function is a function (a block of code) that always returns the same result if the same arguments are passed. It does not depend on any state, or data change during a program’s execution rather it only depends on its input arguments.

- Also a pure function does not produce any observable side effects such as network requests or data mutation etc.
```

- String Operations
```a
.concat()
.split()
.indexOf()
.lastIndexOf()
.substring()
.trim()
.slice()
```

- Array Operations
```a
Stack vs. Queue:
- A stack is a data structure that holds a list of elements. A stack works based on the LIFO principle i.e., Last In, First out, meaning that the most recently added element is the first one to remove.
- A queue is an ordered list of elements where an element is inserted at the end of the queue and is removed from the front of the queue. A queue works based on the first-in, first-out (FIFO) principle, which is different from a stack, which works based on the last-in, first-out (LIFO) principle.

Array Operations:
.splice()
.sort()
.indexOf()
.every()
.some()
.filter()
.reduce()
.map()
.forEach()
.join()
```

- Error handling
```a
- try-catch block
- if-else statement
- switch statement
```

- JavaScript Runtime
```a
Execution Context:
When a JavaScript engine executes a script, it creates execution contexts. Each execution context has two phases: the creation phase and the execution phase:
- Creation phase - when a script executes for the first time, the JavaScript engine creates a Global Execution Context. During this creation phase, it performs the following tasks:
	- Create a global object i.e., window in the web browser or global in Node.js.
	- Create a "this" object binding which points to the global object above.
	- Setup a memory heap for storing variables and function references.
	- Store the function declarations in the memory heap and variables within the global execution context with the initial values as undefined.

- Execution phase - during the execution phase, the JavaScript engine executes the code line by line. In this phase, it assigns values to variables and executes the function calls. For every function call, the JavaScript engine creates a new Function Execution Context. The Function Execution Context is similar to the Global Execution Context, but instead of creating the global object, it creates the arguments object that contains a reference to all the parameters passed into the function.

Event loop:
- The setTimeout(), fetch requests, and DOM events are parts of the Web APIs of the web browser.

- The event loop is a constantly running process that monitors both the callback queue and the call stack.

- If the call stack is not empty, the event loop waits until it is empty and places the next function from the callback queue to the call stack. If the callback queue is empty, nothing will happen.

Hoisting:
- Hoisting is JavaScript's default behavior of moving declarations to the top.
- Function declarations, and "var" variables have hoisting. "Let", "const" & function expressions doesn't have hoisting.
```

- Primitive Wrapper Types
```a
- JavaScript provides three primitive wrapper types: Boolean, Number, and String types.

- The primitive wrapper types make it easier to use primitive values including booleans, numbers, and strings.
```

### ES6

- New ES6 syntax: `var`, `let`, and `const`, Rest parameter, Spread operator, Template literals
```a
var:
- have hoisting
- have function scope
- can redeclare

let & const:
- doesn't have hoisting
- have block scope
- can't redeclare
- const cannot change its value

Rest parameter:
- ES6 provides a new kind of parameter so-called rest parameter that has a prefix of three dots (...). A rest parameter allows you to represent an indefinite number of arguments as an array.

Spread operator:
- ES6 provides a new operator called spread operator that consists of three dots (...). The spread operator allows you to spread out elements of an iterable object such as an array,a  map, or a set.

Template literals:
- In ES6, you create a template literal by wrapping your text in backticks (`) and you get the following features:
	- A multiline string: a string that can span multiple lines.
	- String formatting: the ability to substitute part of the string for the values of variables or expressions. This feature is also called string interpolation.
	- HTML escaping: the ability to transform a string so that it is safe to include in HTML.
```

- Destructuring
```a
ES6 provides a new feature called destructing assignment that allows you to destructure properties of an object or elements of an array into individual variables.
```

- ES6 Modules
```a
An ES6 module is a JavaScript file that executes in strict mode only. It means that any variables or functions declared in the module won’t be added automatically to the global scope:

export let message = 'ES6 Modules';
import { message } from './message.js'
```

- ES6 Classes
```a
A JavaScript class is a blueprint for creating objects. A class encapsulates data and functions that manipulate data.

Unlike other programming languages such as Java and C#, JavaScript classes are syntactic sugar over the prototypal inheritance. In other words, ES6 classes are just special functions.
```

- Arrow Functions
```a
ES6 arrow functions provide you with an alternative way to write a shorter syntax compared to the function expression.
```

- Promises & Async/Await
```a
Promise:
- In JavaScript, a promise is an object that returns a value that you hope to receive in the future, but not now.
- Because the value will be returned by the promise in the future, the promise is very well-suited for handling asynchronous operations.
- A promise has three states:
	- Pending: you don’t know if you will complete learning JavaScript by the next month.
	- Fulfilled: you complete learning JavaScript by the next month.
	- Rejected: you don’t learn JavaScript at all.
- A promise starts in the pending state which indicates that the promise hasn’t been completed. It ends with either fulfilled (successful) or rejected (failed) state.

Async/Await:
- An async function is a function declared with the "async" keyword, and the "await" keyword is permitted within it. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.
- Async functions can contain zero or more await expressions. Await expressions make promise-returning functions behave as though they're synchronous by suspending execution until the returned promise is fulfilled or rejected. The resolved value of the promise is treated as the return value of the await expression. Use of async and await enables the use of ordinary try / catch blocks around asynchronous code.
- Async functions always return a promise. If the return value of an async function is not explicitly a promise, it will be implicitly wrapped in a promise.
```

### ES Next

- Private Fields and methods
```a
ES2022 allows you to define private fields for a class. To define a private field, you prefix the field name with the # sign.

Because the declaration is a private field, you can only access it inside that class. In other words, the declared private field is invisible outside of that class.
```

- Object extensions
```a
Object.assign() – copy an object or merge objects.
Object.is() – check if two values are the same value.
```

- Array extensions
```a
Array.of() – improve array creation.
Array.from() – create arrays from array-like or iterable objects.
Array find() – find an element in an array.
Array findIndex() – find the index of an element in an array.
```

- String extensions
```a
String startsWith() – check if a string starts with another string.
String endsWith() – determine if a string ends with another string.
String includes() – check if a string contains another string.
```

- Logical Assignment Operators
```a
ES2021 introduces three logical assignment operators including:

Logical OR assignment operator (||=)
- The logical OR assignment operator (||=) accepts two operands and assigns the right operand to the left operand if the left operand is falsy

Logical AND assignment operator (&&=)
- The logical AND assignment operator only assigns y to x if x is truthy

Nullish coalesing assignment operator (??=)
- The nullish coalescing assignment operator only assigns y to x if x is null or undefined
```

### JavaScript BOM

The Browser Object Model (BOM) is the core of JavaScript on the web. The BOM provides you with objects that expose the web browser’s functionality.

- Window
```a
The global object of JavaScript in the browser is the window object. It means that all variables and functions declared globally with the var keyword become the properties and methods of the window object.

The window object has four properties related to the size of the window:
- The innerWidth and innerHeight properties return the size of the page viewport inside the browser window (not including the borders and toolbars).
- The outerWidth and outerHeight properties return the size of the browser window itself.
```

### JavaScript DOM

- Getting started
```a
The Document Object Model (DOM) is an application programming interface (API) for manipulating HTML documents.

The DOM represents an HTML document as a tree of nodes. The DOM provides functions that allow you to add, remove, and modify parts of the document effectively.

Note that the DOM is cross-platform and language-independent ways of manipulating HTML and XML documents.
```

- Working with Events
```a
An event is an action that occurs in the web browser, which the web browser feedbacks to you so that you can respond to it.

For example, when users click a button on a webpage, you may want to respond to this click event by displaying a dialog box.

Each event may have an event handler which is a block of code that will execute when the event occurs.

An event handler is also known as an event listener. It listens to the event and executes when the event occurs.

Event flow:
- When you click the button, you’re clicking not only the button but also the button’s container, the div, and the whole webpage.
- Event flow explains the order in which events are received on the page from the element where the event occurs and propagated through the DOM tree.
- There are two main event models: event bubbling and event capturing:
	- Event bubbling - an event starts at the most specific element and then flows upward toward the least specific element (the document or even window).
	- Event capturing - an event starts at the least specific element and flows downward toward the most specific element.
```

- Selecting/Traversing/Manipulating elements
```a
Selecting elements:
- getElementById() – select an element by id.
- getElementsByName() – select elements by name.
- getElementsByTagName()  – select elements by a tag name.
- getElementsByClassName() – select elements by one or more class names.
- querySelector()  – select elements by CSS selectors.

Traversing elements:
- Get the parent element – get the parent node of an element.
- Get child elements – get children of an element.
- Get siblings of an element – get siblings of an element.

Manipulating elements:
- createElement() – create a new element.
- appendChild()  – append a node to a list of child nodes of a specified parent node.
- textContent – get and set the text content of a node.
- innerHTML – get and set the HTML content of an element.
- innerHTML vs. createElement – explain the differences beetween innerHTML and createElement when it comes to creating new elements.
- DocumentFragment – learn how to compose DOM nodes and insert them into the active DOM tree.
- insertBefore() – insert a new node before an existing node as a child node of a specified parent node.
- insertAfter() helper function – insert a new node after an existing node as a child node of a specified parent node.
- append() – insert a node after the last child node of a parent node.
- prepend() – insert a node before the first child node of a parent node.
- insertAdjacentHTML() – parse a text as HTML and insert the resulting nodes into the document at a specified position.
- replaceChild() – replace a child element by a new element.
- cloneNode() – clone an element and all of its descendants.
- removeChild() – remove child elements of a node.
```

- Working with Attributes
```a
- HTML Attributes & DOM Object’s Properties – understand the relationship between HTML attributes & DOM object’s properties.
- setAttribute() – set the value of a specified attribute on a element.
- getAttribute() – get the value of an attribute on an element.
- removeAttribute() – remove an attribute from a specified element.
- hasAttribute() – check if an element has a specified attribute or not.
```

- Scripting Web Forms
```a
The <form> element has two important attributes: action and method.

The action attribute specifies a URL that will process the form submission. In this example, the action is the /signup URL.
The method attribute specifies the HTTP method to submit the form with. Usually, the method is either post or get.
```

### Client-server communication

- What is HTTP?
```a
The Hypertext Transfer Protocol (HTTP) is the foundation of the World Wide Web, and is used to load web pages using hypertext links. HTTP is an application layer protocol designed to transfer information between networked devices and runs on top of other layers of the network protocol stack. A typical flow over HTTP involves a client machine making a request to a server, which then sends a response message.

An HTTP protocol is:
- stateless
- conectionless
- media independent
```

- HTTP request/response: headers, methods, body, status
```a
HTTP request:
- An HTTP request is the way internet communications platforms such as web browsers ask for the information they need to load a website.
- Each HTTP request made across the Internet carries with it a series of encoded data that carries different types of information. A typical HTTP request contains:
	- HTTP version type
	- a URL
	- an HTTP method - GET, POST, PUT, DELETE, PATCH, HEADERS, OPTIONS
	- HTTP request headers - HTTP headers contain text information stored in key-value pairs, and they are included in every HTTP request (and response, more on that later). These headers communicate core information, such as what browser the client is using what data is being requested.
	- Optional HTTP body - The body of a request is the part that contains the ‘body’ of information the request is transferring. The body of an HTTP request contains any information being submitted to the web server, such as a username and password, or any other data entered into a form.

HTTP response:
- An HTTP response is what web clients (often browsers) receive from an Internet server in answer to an HTTP request. These responses communicate valuable information based on what was asked for in the HTTP request.
- A typical HTTP response contains:
	- an HTTP status code - HTTP status codes are 3-digit codes most often used to indicate whether an HTTP request has been successfully completed. Status codes are broken into the following 5 blocks:
		- 1xx Informational
		- 2xx Success
		- 3xx Redirection
		- 4xx Client Error
		- 5xx Server Error
	- HTTP response headers - Much like an HTTP request, an HTTP response comes with headers that convey important information such as the language and format of the data being sent in the response body.
	- optional HTTP body - Successful HTTP responses to ‘GET’ requests generally have a body which contains the requested information. In most web requests, this is HTML data which a web browser will translate into a web page.
```

- Authorization: jwt, session, cookie
```a
JWT:
- JSON Web Token (JWT) is an open standard that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.
- Although JWTs can be encrypted to also provide secrecy between parties, we will focus on signed tokens. Signed tokens can verify the integrity of the claims contained within it, while encrypted tokens hide those claims from other parties. When tokens are signed using public/private key pairs, the signature also certifies that only the party holding the private key is the one that signed it.
- When should you use JSON Web Tokens?
		- Authorization: This is the most common scenario for using JWT.
		- Information Exchange: JSON Web Tokens are a good way of securely transmitting information between parties.
- What is the JSON Web Token structure?
		- Header
		- Payload
		- Signature

Session:
- In the session based authentication, the server will create a session for the user after the user logs in. The session id is then stored on a cookie on the user’s browser. While the user stays logged in, the cookie would be sent along with every subsequent request. The server can then compare the session id stored on the cookie against the session information stored in the memory to verify user’s identity and sends response with the corresponding state!

Cookie:
- A cookie is a small piece of data created by a server and sent to your browser when you visit a website. Browsers often need to store and send it back to the server to tell that the request is coming from the same browser, to keep the user authenticated. We read the browser cookies as “key-value” pairs.

- A Cookie-based authentication uses the HTTP cookies to authenticate the client requests and maintain session information on the server over the stateless HTTP protocol.

- Here is a logical flow of the cookie-based authentication process:
	- The client sends a login request with credentials to the backend server.
	- The server then validates the credentials. If the login is successful, the web server will create a session in the database and include a Set-Cookie header on the response containing a unique ID in the cookie object.
	- The browser saves the cookie locally. As long as the user stays logged in, the client needs to send the cookie in all the subsequent requests to the server. The server then compares the session ID stored in the cookie against the one in the database to verify the validity.
	- During the logout operation, the server will make the cookie expire by deleting it from the database.

```

- CRUD
```a
CRUD (Create, Read, Update, Delete) is an acronym for ways one can operate on stored data. It is a mnemonic for the four basic functions of persistent storage. CRUD typically refers to operations performed in a database or datastore, but it can also apply to higher level functions of an application such as soft deletes where data is not actually deleted but marked as deleted via a status.
```

- REST
```a
- REST, or REpresentational State Transfer, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other.

- REST requires that a client make a request to the server in order to retrieve or modify data on the server. A request generally consists of:
- an HTTP verb, which defines what kind of operation to perform
- a header, which allows the client to pass along information about the request
- a path to a resource
- an optional message body containing data

HTTP Verbs:
There are 4 basic HTTP verbs we use in requests to interact with resources in a REST system:
- GET — retrieve a specific resource (by id) or a collection of resources
- POST — create a new resource
- PUT — update a specific resource (by id)
- DELETE — remove a specific resource by id
```

### Design patterns

- Singleton Pettern
```a
The Singleton Pattern limits the number of instances of a particular object to just one. This single instance is called the singleton.

A singleton should be immutable by the consuming code, and there should be no danger of instantiating more than one of them.

An example for Singleton Pattern is the Redux Store.
```

- Observer Pattern
```a
The Observer pattern offers a subscription model in which objects subscribe to an event and get notified when the event occurs. This pattern is the cornerstone of event driven programming, including JavaScript. The Observer pattern facilitates good object-oriented design and promotes loose coupling.
```

- Module Pattern
```a
The Module Pattern is one of the important patterns in JavaScript. It is a commonly used Design Pattern which is used to wrap a set of variables and functions together in a single scope.
- It is used to define objects and specify the variables and the functions that can be accessed from outside the scope of the function.
- We expose certain properties and function as public and can also restrict the scope of properties and functions within the object itself, making them private.
- This means that those variables cannot be accessed outside the scope of the function.
- We can achieve data hiding an abstraction using this pattern
```

- Prototype Pattern
```a
The Prototype Pattern creates new objects, but rather than creating non-initialized objects it returns objects that are initialized with values it copied from a prototype - or example - object. The Prototype pattern is also referred to as the Properties pattern.
```

- Factory Pattern
```a
A Factory Method creates new objects as instructed by the client. One way to create objects in JavaScript is by invoking a constructor function with the new operator. There are situations however, where the client does not, or should not, know which one of several candidate objects to instantiate. The Factory Method allows the client to delegate object creation while still retaining control over which type to instantiate.
```

### GIT

- What is Version Control?
```a
Version control, also known as source control, is the practice of tracking and managing changes to software code. Version control systems are software tools that help software teams manage changes to source code over time. As development environments have accelerated, version control systems help software teams work faster and smarter. They are especially useful for DevOps teams since they help them to reduce development time and increase successful deployments.

Version control software keeps track of every modification to the code in a special kind of database. If a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the mistake while minimizing disruption to all team members.
```

- What is Git?
```a
Git is the most commonly used version control system. Git tracks the changes you make to files, so you have a record of what has been done, and you can revert to specific versions should you ever need to. Git also makes collaboration easier, allowing changes by multiple people to all be merged into one source.
```

- Getting and Creating Projects
```a
- git clone - Clone a repository into a new directory
- git init - Create an empty Git repository or reinitialize an existing one
```

- Basic Snapshotting
```a
- git add - Add file contents to the index
- git status - Show the working tree status
- git diff - Show changes between commits, commit and working tree, etc
- git commit - Record changes to the repository
- git notes - Add or inspect object notes
- git restore - Restore working tree files
- git reset - Reset current HEAD to the specified state
- git rm - Remove files from the working tree and from the index
- git mv - Move or rename a file, a directory, or a symlink
```

- Branching and Merging
```a
- git branch - List, create, or delete branches
- git checkout - Switch branches or restore working tree files
- git switch - Switch branches
- git merge - Join two or more development histories together
- git mergetool - Run merge conflict resolution tools to resolve merge conflicts
- git log - Show commit logs
- git stash - Stash the changes in a dirty working directory away
- git tag - Create, list, delete or verify a tag object signed with GPG
- git worktree - Manage multiple working trees
```

- Sharing and Updating Projects
```a
- git fetch - Download objects and refs from another repository
- git pull - Fetch from and integrate with another repository or a local branch
- git push - Update remote refs along with associated objects
- git remote - Manage set of tracked repositories
- git submodule - Initialize, update or inspect submodules
```

- Git Flow
```a
Giflow is an alternative Git branching model that involves the use of feature branches and multiple primary branches. Under this model, developers create a feature branch and delay merging it to the main trunk branch until the feature is complete.

- git flow init - Executing this on an existing repo will create the develop branch
- git flow feature start feature_branch - Creating a feature branch
- git flow feature finish feature_branch - Finishing a feature branch
```


## Advanced

### ES6

- Proxy & Reflection
```a
Proxy:
- A JavaScript Proxy is an object that wraps another object (target) and intercepts the fundamental operations of the target object.
- The fundamental operations can be the property lookup, assignment, enumeration, and function invocations, etc.
- let proxy = new Proxy(target, handler);
	- target – is an object to wrap.
	- handler – is an object that contains methods to control the behaviors of the target. The methods inside the handler object are called traps.

Reflection:
- In computer programming, reflection is the ability of a program to manipulate variables, properties, and methods of objects at runtime.
- Prior to ES6, JavaScript already has reflection features even though they were not officially called that by the community or the specification. For example, methods like Object.keys(), Object.getOwnPropertyDescriptor(), and Array.isArray() are the classic reflection features.
- ES6 introduces a new global object called Reflect that allows you to call methods, construct objects, get and set properties, manipulate and extend properties.
- The Reflect API is important because it allows you to develop programs and frameworks that are able to handle dynamic code.
- Unlike the most global objects, the Reflect is not a constructor. It means that you cannot use Reflect with the new operator or invoke the Reflect as a function.  It is similar to the Math and JSON objects. All the methods of the Reflect object are static.
	- Reflect.apply() – call a function with specified arguments.
	- Reflect.construct() – act like the new operator, but as a function. It is equivalent to calling new target(...args).
	- Reflect.defineProperty() – is similar to Object.defineProperty(), but return a Boolean value indicating whether or not the property was successfully defined on the object.
	- Reflect.deleteProperty() – behave like the delete operator, but as a function. It’s equivalent to calling the  delete objectName[propertyName].
	- Reflect.get() – return the value of a property.
	- Reflect.getOwnPropertyDescriptor() – is similar to Object.getOwnPropertyDescriptor(). It returns a property descriptor of a property if the property exists on the object, or undefined otherwise.
	- Reflect.getPrototypeOf() – is the same as Object.getPrototypeOf().
	- Reflect.has() – work like the in operator, but as a function. It returns a boolean indicating whether an property (either owned or inherited) exists.
	- Reflect.isExtensible() – is the same as Object.isExtensible().
	- Reflect.ownKeys() – return an array of the owned property keys (not inherited) of an object.
	- Reflect.preventExtensions() – is similar to Object.preventExtensions(). It returns a Boolean.
	- Reflect.set() – assign a value to a property and return a Boolean value which is true if the property is set successfully.
	- Reflect.setPrototypeOf() – set the prototype of an object.
```

### ESNext

- Iterators & Generators
```a
Iterators:
- The main method of an iterator interface is the next() that returns the {value, done} object, where done is a boolean indicating whether the end of the sequence is reached and value is the yielded value in the sequence.
- The synchronous data means that the next value in the sequence and the done state is known at the time the next() method returns.
- Besides the synchronous data sources, JavaScript often has to access asynchronous data sources like I/O access. For the asynchronous data sources, the value and done state of the iterator is often unknown at the time the next() method returns.
- To deal with the asynchronous data sources, ES2018 introduced the asynchronous iterator (or async iterator) interface.
- An async iterator is like an iterator except that its next() method returns a promise that resolves to the {value, done} object.

Generators:
- A regular generator is a function that can pause midway and continues from where it paused.
- An async generator is similar to a regular generator except that its next() method returns a Promise. To iterate over an async generator, you use the for await...of statement.
- An async generator is similar to a regular generator with the following differences:
	- The async keyword is placed in front of the function keyword.
	- The yield returns a Promise , instead of a value. The Promise is typically a wrapper of an asynchronous operation.
```

- Symbol
```a
- ES6 added Symbol as a new primitive type. Unlike other primitive types such as number, boolean, null, undefined, and string, the symbol type doesn’t have a literal form.
- To create a new symbol, you use the global Symbol() function.
- The Symbol() function creates a new unique value each time you call it.
- The Symbol() function accepts a description as an optional argument. The description argument will make your symbol more descriptive.
- You can access the symbol’s description property using the toString() method. The console.log() method calls the toString() method of the symbol implicitly.
```

- BigInt
```a
- The bigint is the primitive type like number, string, symbol, boolean undefined, and null.
- To make a BigInt, you append n to the end of the number literal.
- Alternatively, you can call the function BigInt().
```

- Numeric separator
```a
- The numeric separator allows you to create a visual separation between groups of digits by using underscores (_) as separators.
- const budget = 1_000_000_000;
```

- Collections
```a
Map:
- By definition, a Map object holds key-value pairs where values of any type can be used as either keys or values. In addition, a Map object remembers the original insertion order of the keys.
- The Map() accepts an optional iterable object whose elements are key-value pairs.
- Useful Map methods:
	- clear()
	- delete(key)
	- entries()
	- forEach(callback[, thisArg])
	- get(key)
	- has(key)
	- keys()
	- set(key, value)
	- values()

Set:
- ES6 provides a new type named Set that stores a collection of unique values of any type.
- The Set constructor also accepts an optional iterable object. If you pass an iterable object to the Set constructor, all the elements of the iterable object will be added to the new set.
- Useful Set methods:
	- add(value)
	- clear()
	- delete(value)
	- entries()
	- forEach(callback [, thisArg])
	- has(value)
	- keys()
	- [@@iterator]
```

- Top-level await
```a
ES2020 introduced the top-level await feature that allows a module to behave like an async function. A module that imports the top-level await module will wait for it to load before evaluating its body.
```

### JavaScript BOM

- Location
```a
The Location object represents the current location (URL) of a document. You can access the Location object by referencing the location property of the window or document object.

Both window.location and document.location link to the same Location object.

JavaScript Location properties:
- location.href
- location.protocol
- location.host
- location.port
- location.pathname
- location.search
- location.hash
- location.origin
- location.username
- location.password
```

- Navigator
```a
The JavaScript Navigator provides information about the web browser and its capabilities. You can reference the Navigator object via the read-only window.navigator property.

The Navigator object has properties that convey the browser’s information. For example, the userAgent is a property of the window.navigator object. It is a long string that identifies the web browser.
```

- Screen
```a
The Screen object provides the attributes of the screen on which the current window is being rendered.

To access the Screen object, you use the screen property of the window object: window.screen
```

- History
```a
When you launch the web browser and open a new webpage, the web browser creates a new entry in its history stack.

If you navigate to another webpage, the web browser also creates a new entry in the history stack.

The history stack stores the current page and previous pages that you visited.

To manipulate the history stack, you use the history object which is a property of the window object: window.history

For the security reason, it’s not possible to query the pages that a user have visited. However, you can use the history object to navigate back and forth without knowing the exact URL.

The history object provides three methods for navigating between pages in the history stack:
- back()
- forward()
- go()
```

### HTTP

- Cross-Origin Resource Sharing (CORS)
```a
Cross-Origin Resource Sharing (CORS) is an HTTP-header based mechanism that allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources. CORS also relies on a mechanism by which browsers make a "preflight" request to the server hosting the cross-origin resource, in order to check that the server will permit the actual request. In that preflight, the browser sends headers that indicate the HTTP method and headers that will be used in the actual request.

For security reasons, browsers restrict cross-origin HTTP requests initiated from scripts. For example, XMLHttpRequest and the Fetch API follow the same-origin policy. This means that a web application using those APIs can only request resources from the same origin the application was loaded from unless the response from other origins includes the right CORS headers.
```

- HTTPS
```a
Hypertext transfer protocol secure (HTTPS) is the secure version of HTTP, which is the primary protocol used to send data between a web browser and a website. HTTPS is encrypted in order to increase security of data transfer. This is particularly important when users transmit sensitive data, such as by logging into a bank account, email service, or health insurance provider.

Any website, especially those that require login credentials, should use HTTPS. In modern web browsers such as Chrome, websites that do not use HTTPS are marked differently than those that are. Look for a green padlock in the URL bar to signify the webpage is secure. Web browsers take HTTPS seriously; Google Chrome and other browsers flag all non-HTTPS websites as not secure.

HTTPS uses an encryption protocol to encrypt communications. The protocol is called Transport Layer Security (TLS), although formerly it was known as Secure Sockets Layer (SSL). This protocol secures communications by using what’s known as an asymmetric public key infrastructure. This type of security system uses two different keys to encrypt communications between two parties:
- The private key - this key is controlled by the owner of a website and it’s kept, as the reader may have speculated, private. This key lives on a web server and is used to decrypt information encrypted by the public key.
- The public key - this key is available to everyone who wants to interact with the server in a way that’s secure. Information that’s encrypted by the public key can only be decrypted by the private key.
```

- HTTP2
```a
HTTP/2 was released in 2015 as a major revision to the HTTP/1.1 protocol. It was derived from the SPDY protocol as a way to improve the online experience by speeding up page loads and reducing round-trip time (RTT), especially on resource-heavy web pages.

HTTP/2 improved on HTTP/1.1 in a number of ways that allowed for speedier content delivery and improved user experience, including:
- Binary protocols – Binary protocols consume less bandwidth, are more efficiently parsed and are less error-prone than the textual protocols used by HTTP/1.1. Additionally, they can better handle elements such as whitespace, capitalization and line endings.
- Multiplexing – HTTP/2 is multiplexed, i.e., it can initiate multiple requests in parallel over a single TCP connection. As a result, web pages containing several elements are delivered over one TCP connection. These capabilities solve the head-of-line blocking problem in HTTP/1.1, in which a packet at the front of the line blocks others from being transmitted.
- Header compression – HTTP/2 uses header compression to reduce the overhead caused by TCP’s slow-start mechanism.
- Server push – HTTP/2 servers push likely-to-be-used resources into a browser’s cache, even before they’re requested. This allows browsers to display content without additional request cycles.
- Increased security – Web browsers only support HTTP/2 via encrypted connections, increasing user and application security.
```

- HTTP Cache
```a
Cache-control is an HTTP header used to specify browser caching policies in both client requests and server responses. Policies include how a resource is cached, where it’s cached and its maximum age before expiring (i.e., time to live).

The cache-control header is broken up into directives, the most common of which are detailed below:
- Cache-Control: Max-Age - The max-age request directive defines, in seconds, the amount of time it takes for a cached copy of a resource to expire. After expiring, a browser must refresh its version of the resource by sending another request to a server.
- Cache-Control: No-Cache - The no-cache directive means that a browser may cache a response, but must first submit a validation request to an origin server.
- Cache-Control: No-Store - The no-store directive means browsers aren’t allowed to cache a response and must pull it from the server each time it’s requested. This setting is usually used for sensitive data, such as personal banking details.
- Cache-Control: Public - The public response directive indicates that a resource can be cached by any cache.
- Cache-Control: Private - The private response directive indicates that a resource is user specific—it can still be cached, but only on a client device. For example, a web page response marked as private can be cached by a desktop browser, but not a content delivery network (CDN).
```

### Other

- Regular Expressions
```a
A regular expression is a string that describes a pattern e.g., email addresses and phone numbers.

In JavaScript, regular expressions are objects. JavaScript provides the built-in RegExp type that allows you to work with regular expressions effectively.

Regular expressions are useful for searching and replacing strings that match a pattern. They have many useful applications.

For example, you can use regular expressions to extract useful information in web scraping like product prices. Or you can use regular expressions to validate form fields like email addresses and phone numbers.
```