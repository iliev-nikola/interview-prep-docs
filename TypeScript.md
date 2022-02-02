# TypeScript topics

Source: 
- https://www.typescripttutorial.net/
- https://www.typescriptlang.org/

## Basics

- What is TypeScript?
```a
TypeScript is a super set of JavaScript.

TypeScript builds on top of JavaScript. First, you write the TypeScript code. Then, you compile the TypeScript code into plain JavaScript code using a TypeScript compiler.

Once you have the plain JavaScript code, you can deploy it to any environments that JavaScript runs.

TypeScript files use the .ts extension rather than the .js extension of JavaScript files.

Why TypeScript?
The main goals of TypeScript are:
- Introduce optional types to JavaScript.
- Implement planned features of future JavaScript, a.k.a. ECMAScript Next or ES Next to the current JavaScript.

1. TypeScript improves your productivity while helping avoid bugs:
- Types increase productivity by helping you avoid many mistakes. By using types, you can catch bugs at the compile-time instead of having them occurring at runtime.

2. TypeScript brings the future JavaScript to today:
TypeScript supports the upcoming features planned in the ES Next for the current JavaScript engines. It means that you can use the new JavaScript features before web browsers (or other environments) fully support them.
```

- Basic Types
```a
1. Number Type:
All numbers in TypeScript are either floating-point values or big integers. The floating-point numbers have the type number while the big integers get the type bigint.
The number type
The following shows how to declare a variable that holds a floating-point value:
```
```
let price: number;
```
```a
Or you can initialize the price variable to a number:
```
```
let price = 9.95;
```
```a
As in JavaScript, TypeScript supports the number literals for decimal, hexadecimal, binary, and octal literals:
1.1. Decimal numbers:
The following shows some decimal numbers:
```
```
let counter: number = 0;
let x: number = 100, 
    y: number = 200;
```
```a
1.2. Binary Numbers:
The binary number uses a leading zero followed by a lowercase or uppercase letter “B” e.g., 0b or 0B :
```
```
let bin = 0b100;
let anotherBin: number = 0B010;
```
```a
Note that the digit after 0b or 0B must be 0 or 1.

1.3 Octal Numbers
An octal number uses a leading zero followed the letter o (since ES2015) 0o. The digits after 0o are numbers in the range 0 through 7:
```
```
let octal: number = 0o10;
```
```a
1.4. Hexadecimal numbers:
Hexadecimal numbers use a leading zero followed by a lowercase or uppercase letter X (0x or 0X). The digits after the 0x must be in the range (0123456789ABCDEF). For example:
```
```
let hexadecimal: number = 0XA;
```
```a
JavaScript has the Number type (with the letter N in uppercase) that refers to the non-primitive boxed object. You should not use this Number type as much as possible in TypeScript.

1.5. Big Integers:
The big integers represent the whole numbers larger than 2 (multiplied by itself 53 times) minus 1. A Big integer literal has the n character at the end of an integer literal like this:
```
```
let big: bigint = 9007199254740991n;
```
```a
2. String Type
- In TypeScript, all strings get the string type.
- Like JavaScript, TypeScript uses double quotes ("), single quotes ('), and backtick (`) to surround string literals.
```
```a
3. Boolean Type
The TypeScript boolean type allows two values: true and false. It’s one of the primitive types in TypeScript. For example:
```
```
let pending: boolean;
pending = true;
// after a while
// ..
pending = false;
```
```a
JavaScript has the Boolean type that refers to the non-primitive boxed object. The Boolean type has the letter B in uppercase, which is different from the boolean type.

It’s a good practice to avoid using the Boolean type.
```
```a
4. Object Type
- The TypeScript object type represents any value that is not a primitive value.
- The Object type, however, describes functionality that available on all objects.
- The empty type {} refers to an object that has no property on its own.
```
```
let employee: {
    firstName: string;
    lastName: string;
    age: number;
    jobTitle: string;
} = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    jobTitle: 'Web Developer'
};
```
```a
5. Array Type
- In TypeScript, an array is an ordered list of values. An array can store a mixed type of values.
- To declare an array of a specific type, you use the let arr: type[] syntax.
```
```a
6. Tuple Type
A tuple works like an array with some additional considerations:

The number of elements in the tuple is fixed.
The types of elements are known, and need not be the same.
For example, you can use a tuple to represent a value as a pair of a string and a number:
```
```
let skill: [string, number];
skill = ['Programming', 5];
```
```a
7. Enum Type
An enum is a group of named constant values. Enum stands for enumerated type.

To define an enum, you follow these steps:
- First, use the enum keyword followed by the name of the enum.
- Then, define constant values for the enum.

The following shows the syntax for defining an enum:
```
```
enum name { constant1, constant2, ... };
```
```a
8. Any Type
Sometimes, you may need to store a value in a variable. But you don’t know its type at the time of writing the program. And the unknown value may come from a third party API or user input.

In this case, you want to opt-out of the type checking and allow the value to pass through the compile-time check.

To do so, you use the any type. The any type allows you to assign a value of any type to a variable:
```
```a
9. Void Type
The void type denotes the absence of having any type at all. It is a little like the opposite of the any type.

Typically, you use the void type as the return type of functions that do not return a value.
```
```a
10. Never Type
The never type is a type that contains no values. Because of this, you cannot assign any value to a variable with a never type.

Typically, you use the never type to represent the return type of a function that always throws an error.

The never type represents the return type of a function that always throws an error or a function that contains an indefinite loop.
```
```a
11. Union Type
Sometimes, you will run into a function that expects a parameter that is either a number or a string.

To resolve this, you can use the TypeScript union type. The union type allows you to combine multiple types into one type.

For example, the following variable is of type number or string:
```
```
let result: number | string;
result = 10; // OK
result = 'Hi'; // also OK
result = false; // a boolean value, not OK
```
```a
A union type describes a value that can be one of several types, not just two. For example number | string | boolean is the type of a value that can be a number, a string, or a boolean.
```
```a
12. Type Aliases
Type aliases allow you to create a new name for an existing type. The following shows the syntax of the type alias:
```
```
type alias = existingType;
```
```a
The existing type can be any valid TypeScript type.

The following example use the type alias chars for the string type:
```
```
type chars = string;
let messsage: chars; // same as string type
```
```a
It’s useful to create type aliases for union types. For example:
```
```
type alphanumeric = string | number;
let input: alphanumeric;
input = 100; // valid
input = 'Hi'; // valid
input = false; // Compiler error
```
```a
13. String Literal Types
- A TypeScript string literal type defines a type that accepts specified string literal.
- Use the string literal types with union types and type aliases to define types that accept a finite set of string literals.
```
```
type MouseEvent: 'click' | 'dblclick' | 'mouseup' | 'mousedown';
let mouseEvent: MouseEvent;
mouseEvent = 'click'; // valid
mouseEvent = 'dblclick'; // valid
mouseEvent = 'mouseup'; // valid
mouseEvent = 'mousedown'; // valid
mouseEvent = 'mouseover'; // compiler error

let anotherEvent: MouseEvent;
```

- Functions
```a
1. Functions:
TypeScript functions are the building blocks of readable, maintainable, and reusable code.

Unlike JavaScript, TypeScript allows you to use type annotations in parameters and return value of a function.

Let’s see the following add() function example:
```
```
function add(a: number, b: number): number {
    return a + b;
}
```
```a
2. Optional Parameters:
In JavaScript, you can call a function without passing any arguments even though the function specifies parameters. Therefore, JaveScript supports the optional parameters by default.

In TypeScript, the compiler checks every function call and issues an error in the following cases:
- The number of arguments is different from the number of parameters specified in the function.
- Or the types of arguments are not compatible with the types of function parameters.

Because the compiler thoroughly checks the passing arguments, you need to annotate optional parameters to instruct the compiler not to issue an error when you omit the arguments.

To make a function parameter optional, you use the ? after the parameter name.

3. Default Parameters:
- Use default parameter syntax parameter:=defaultValue if you want to set the default initialized value for the parameter.
- Default parameters are optional.
- To use the default initialized value of a parameter, you omit the argument when calling the function or pass the undefined into the function.

4. Rest Parameters:
A rest parameter allows you a function to accept zero or more arguments of the specified type. In TypeScript, rest parameters follow these rules:
- A function has only one rest parameter.
- The rest parameter appears last in the parameter list.
- The type of the rest parameter is an array type.

To declare a rest parameter, you prefix the parameter name with three dots and use the array type as the type annotation:
```
```
function getTotal(...numbers: number[]): number {
    let total = 0;
    numbers.forEach((num) => total += num);
    return total;
}
```

- Classes
```a
Use class keyword to define a class in TypeScript.
TypeScript leverages the ES6 class syntax and adds type annotations to make the class more robust.
```
```a
Access modifiers change the visibility of the properties and methods of a class. TypeScript provides three access modifiers:
- private - limits the visibility to the same-class only. When you add the private modifier to a property or method, you can access that property or method within the same class. Any attempt to access private properties or methods outside the class will result in an error at compile time.
- protected - allows properties and methods of a class to be accessible within same class and within subclasses.
- public - allows class properties and methods to be accessible from all locations. If you don’t specify any access modifier for properties and methods, they will take the public modifier by default.

Note that TypeScript controls the access logically during compilation time, not at runtime.
```
```a
TypeScript provides the readonly modifier that allows you to mark the properties of a class immutable. The assignment to a readonly property can only occur in one of two places:
- In the property declaration.
- In the constructor of the same class.

To mark a property as immutable, you use the readonly keyword. The following shows how to declare a readonly property in the Person class:

class Person {
    readonly birthDate: Date;

    constructor(birthDate: Date) {
        this.birthDate = birthDate;
    }
}
```
```a
- Static properties:
Unlike an instance property, a static property is shared among all instances of a class.

To declare a static property, you use the static keyword. To access a static property, you use the className.propertyName syntax.

- Static methods:
Similar to the static property, a static method is also shared across instances of the class. To declare a static method, you use the static keyword before the method name.
```
```a
An abstract class is typically used to define common behaviors for derived classes to extend. Unlike a regular class, an abstract class cannot be instantiated directly.
```

- Interfaces
```a
TypeScript interfaces define the contracts within your code. They also provide explicit names for type checking.
```
```
interface Person {
    firstName: string;
    lastName: string;
}
```

## Advanced

- Advanced types: Intersection, Guard, Casting, Assertions
```a
1. Intersection
An intersection type creates a new type by combining multiple existing types. The new type has all features of the existing types.

To combine types, you use the & operator as follows:
```
```
type typeAB = typeA & typeB;
```
```a
2. Type Guard
Type Guards allow you to narrow down the type of a variable within a conditional block.

Use the typeof and instanceof operators to implement type guards in the conditional blocks
```
```
type alphanumeric = string | number;

function add(a: alphanumeric, b: alphanumeric) {
    if (typeof a === 'number' && typeof b === 'number') {
        return a + b;
    }

    if (typeof a === 'string' && typeof b === 'string') {
        return a.concat(b);
    }

    throw new Error('Invalid arguments. Both arguments must be either numbers or strings.');
}
```
```a
3. Type Casting
JavaScript doesn’t have a concept of type casting because variables have dynamic types. However, every variable in TypeScript has a type. Type castings allow you to convert a variable from one type to another.

In TypeScript, you can use the as keyword or <> operator for type castings.
```
```
let input = document.querySelector('input[type="text"]') as HTMLInputElement;
```
```a
4. Type Assertions
- Type assertions instruct the compiler to treat a value as a specified type.
- Type assertions do not carry any type conversion.
- Type assertions use the as keyword or an angle bracket <> syntax.
```
```
let netPrice = getNetPrice(100, 0.05, true) as string;

let netPrice = <number>getNetPrice(100, 0.05, false);
```

- Generics
```a
1. The following shows a generic function that returns the random element from an array of type T:
```
```
function getRandomElement<T>(items: T[]): T {
    let randomIndex = Math.floor(Math.random() * items.length);
    return items[randomIndex];
}
```
```a
This function uses type variable T. The T allows you to capture the type that is provided at the time of calling the function. Also, the function uses the T type variable as its return type.

This getRandomElement() function is generic because it can work with any data type including string, number, objects,…

2. The following shows how to use the getRandomElement() with an array of numbers:
```
```
let numbers = [1, 5, 7, 4, 2, 9];
let randomEle = getRandomElement<number>(numbers); 
console.log(randomEle);

3. Generic constraints in TypeScript:
Instead of working with all types, you may want to add a constraint to the merge() function so that it works with objects only.

To do this, you need to list out the requirement as a constraint on what U and V types can be.

In order to denote the constraint, you use the extends keyword. For example:
```
```
function merge<U extends object, V extends object>(obj1: U, obj2: V) {
    return {
        ...obj1,
        ...obj2
    };
}
```
```a
- Use extends keyword to constrain the type parameter to a specific type.
- Use extends keyof to constrain a type that is the property of another object.

4. Generic interfaces that describe object properties:
The following show how to declare a generic interface that consists of two members key and value with the corresponding types K and V:
```
```
interface Pair<K, V> {
    key: K;
    value: V;
}
```

- Type manipulations
```a
TypeScript’s type system is very powerful because it allows expressing types in terms of other types.

The simplest form of this idea is generics, we actually have a wide variety of type operators available to use. It’s also possible to express types in terms of values that we already have.

By combining various type operators, we can express complex operations and values in a succinct, maintainable way. In this section we’ll cover ways to express a new type in terms of an existing type or value.
- Generics - Types which take parameters
- Keyof Type Operator - Using the keyof operator to create new types
- Typeof Type Operator - Using the typeof operator to create new types
- Indexed Access Types - Using Type['a'] syntax to access a subset of a type
- Conditional Types - Types which act like if statements in the type system
- Mapped Types - Creating types by mapping each property in an existing type
- Template Literal Types - Mapped types which change properties via template literal strings
```

- Modules
```a
Since ES6, JavaScript started supporting modules as the native part of the language. TypeScript shares the same module concept with JavaScript.

A TypeScript module can contain both declarations and code. A module executes within its own scope, not in the global scope. It means that when you declare variables, functions, classes, interfaces, etc., in a module, they are not visible outside the module unless you explicitly export them using export statement.

On the other hand, if you want to access variables, functions, classes, etc., from a module, you need to import them using the import statement.

Like ES6, when TypeScript file contains a top-level import or export, it is treated as a module.
```
```
interface Validator {
    isValid(s: string): boolean
}

export { Validator as StringValidator };
```
```
import { Validator } from './Validator';

class EmailValidator implements Validator {
    isValid(s: string): boolean {
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return emailRegex.test(s);
    }
}

export { EmailValidator };
```

- TypeScript in Node.js
```a
1. First, create a new directory called "nodets".

2. Second, create two sub-directories under the "nodets" called "build" and "src".

You’ll store the TypeScript code in the "src" directory.

Once the TypeScript compiler compiles the source TypeScript files, it will store the output files in the "build" directory.

2. Configure the TypeScript compiler
From the Terminal on macOS and Linux or Command Prompt on Windows, run the following command in the "nodets" directory to create the "tsconfig.json" file:
```
```bash
tsc --init
```
```a
You’ll see the tsconfig.json created under the nodets directory:

The "tsconfig.json" file indicates that the directory ("nodets") is the root of the TypeScript project.

When you compile the TypeScript files, TypeScript compiler will use the options in the "tsconfig.json" to compile the project.

Now, you can open the "tsconfig.json" file. There are many options. In this tutorial, you’ll focus on these two options:
- "rootdir" – specifies the root directory of the TypeScript input files.
- "outdir" -stores the JavaScript output files.

These options are commented by default. And you’ll need to uncomment ( remove the "//" at the beginning of the line) and change them as follows:

For the "outDir" option:
```
```
"outDir": "./build"
```
```a
And for the "rootDir" option:
```
```
"rootDir": "./src"
```
```a
To verify the new configuration, you can create a new file called "app.ts" under the "./src" directory and place the following code:
```
```
console.log('Node.js TypeScript');
```
```a
And then run the following command to execute the TypeScript compiler. It’ll compile all the files stored in the "src" directory:
```
```bash
tsc
```
```a
If the configuration is correct, you’ll see the "app.js" generated under the "./build" directory.

To run the "app.js", you navigate to the "build" directory and execute the following command:
```
```
node app.js
```
```a
You’ll see the following output:
```
```
Node.js TypeScript
```
```a
Every time when you change the TypeScript code, you need to:
- Build the project.
- Run the JavaScript output files.

This is time-consuming.

Luckly, you can automate the whole process using some Node.js modules.

3. Install Node.js modules
The "nodemon" module allows you to automatically restart the application when you change the JavaScript source code.

The "concurrently" module runs multiple commands concurrently.

First, execute the "npm init" command from the root directory of the project:
```
```bash
npm init --yes
```
```a
Next, install the nodemon and concurrently module:
```
```bash
npm install --g nodemon concurrently
```
```a
It’ll take some time to install. Once the installation completes.

Note that the "-g" flag will instruct npm to install these two modules globally. This allows you to use them in other projects.

Then, open the "package.json" file, you’ll something like this in the "scripts" option:
```
```
...  
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
},
...
```
```a
After that, change the "scripts" option to the following:
```
```
...
"scripts": {
    "start:build": "tsc -w",
    "start:run": "nodemon build/app.js",
    "start": "concurrently npm:start:*"
},
...
```
```a
This "start:build": "tsc -w" will watch for the changes in the ./src directory and compile them automatically.

This "start:run": "nodemon build/app.js" will automatically run the app.js in the ./build directory whenever the new file is generated.

This "start": "concurrently npm:start:*" runs all the commands that start with npm:start:*, which executes both start:build and start:run commands above.

Since the app.js will be the entry point for the Node.js program, you also need to change the following option in the package.json file to app.js:

From:
```
```
"main": "index.js"
```
```a
To:
```
```
"main": "app.js"
```
```a
Finally, execute the following command:
```
```
npm start
```
```a
To verify the configuration, you change some code in the app.ts. And you’ll see the output in the console.
```