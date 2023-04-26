# What is JavaScript?

JavaScript is a programming language that can be used to create interactive web pages and web applications. It is used on the client side (in the web browser) and on the server side (with Node.js).

JavaScript is a dynamically typed language, which means that you don't have to declare the type of a variable before you use it. You can assign a value of any type to a variable, and the type of the variable will be determined automatically at runtime.

JavaScript uses a syntax that is similar to other programming languages like Java, C++, and Python. It has variables, functions, loops, conditional statements, and other basic programming constructs.

JavaScript has a lot of built-in functions and objects that you can use to perform common tasks like manipulating strings, working with arrays, and accessing the Document Object Model (DOM) of a web page.

To use JavaScript in a web page, you need to include a script tag in the HTML document that references a JavaScript file or contains inline JavaScript code.

You can use JavaScript to create interactive features on a web page, like form validation, animations, and dynamic content that changes based on user input.

There are many popular JavaScript frameworks and libraries that you can use to simplify web development, such as React, Angular, and Vue.js.

# Variables and Data Types

JavaScript supports several data types, including numbers, strings, booleans, null, and undefined. You'll need to understand how to create and manipulate variables that store these data types.

In JavaScript, a variable is a named container that stores a value. You can use variables to store different types of data, including numbers, strings, booleans, null, and undefined.

To create a variable in JavaScript, you use the var, let, or const keyword followed by the variable name. For example:

```js
var myNumber = 10;
let myString = "Hello, world!";
const PI = 3.14;
```

In this example, we've created three variables: myNumber, myString, and PI. myNumber is a number, myString is a string, and PI is a constant (meaning its value cannot be changed).

JavaScript also supports dynamic typing, which means that you can change the data type of a variable simply by assigning a new value to it. For example:

```js
let myVariable = 10; // myVariable is a number
myVariable = "Hello"; // myVariable is now a string
```

It's important to be aware of the different data types in JavaScript, as each type has its own set of operations and behaviors. For example, you can perform mathematical operations on numbers, but you can't perform those same operations on strings.

Overall, understanding variables and data types is a fundamental concept in JavaScript, as it lays the groundwork for working with data and creating dynamic applications.

# Falsy values:

  1. ''
  2. 0
  3. null
  4. undefined
  5. false

# Understand about the scope of variable:

In JavaScript, scope refers to the accessibility of variables, functions, and objects in different parts of your code. There are three types of scope in JavaScript:

## Global Scope:

A variable declared outside of any function, including the main program, is said to have a global scope. Global variables can be accessed from anywhere in your code, including inside functions.

```js
var x = 10; // global variable
function foo() {
  console.log(x); // x can be accessed inside this function
}
foo(); // output: 10
```

## Function Scope:

A variable declared inside a function has function scope. This means that it is only accessible within that function and any nested functions.

```js
function foo() {
  var x = 10; // variable with function scope
  console.log(x); // x can be accessed inside this function
}
foo(); // output: 10
console.log(x); // throws an error as x is not defined outside the function
```

## Block Scope:

Block scope was introduced in ES6 (ECMAScript 2015). A variable declared inside a block (denoted by curly braces {}), such as an if statement or a for loop, has block scope. This means that it is only accessible within that block and any nested blocks.

```js
if (true) {
  let x = 10; // variable with block scope
  console.log(x); // x can be accessed inside this block
}
console.log(x); // throws an error as x is not defined outside the block

```

It's important to understand the different types of scope in JavaScript to avoid naming conflicts and make your code more organized and readable.

# var, let & const:

## var:

var was the original way to declare variables in JavaScript. Variables declared with var have function scope or global scope (if declared outside of a function). This means that they are accessible throughout the entire function or global scope, even if they are declared inside a block. var variables can also be re-declared and reassigned.

```js
function foo() {
  var x = 10; // function scope
  if (true) {
    var x = 20; // re-declares x, still in function scope
    console.log(x); // output: 20
  }
  console.log(x); // output: 20
}
```

## let:

let was introduced in ES6 and provides block scoping. This means that variables declared with let are only accessible within the block they are declared in, including nested blocks. Unlike var, let variables can be reassigned but not re-declared within the same scope.

```js
function foo() {
  let x = 10; // block scope
  if (true) {
    let x = 20; // new x, still in block scope
    console.log(x); // output: 20
  }
  console.log(x); // output: 10
}
```

## const:

const is also introduced in ES6 and provides block scoping like let. However, once a variable is declared with const, its value cannot be reassigned. This makes const useful for declaring variables that should not be changed, such as constants and configuration values.

```js
const PI = 3.14; // block scope, cannot be reassigned
console.log(PI); // output: 3.14
PI = 3.14159; // throws an error as PI cannot be reassigned
```

It's good practice to use let and const instead of var to make your code more organized and avoid naming conflicts. Additionally, using const for variables that shouldn't be reassigned can make your code more robust and less error-prone.

# Assessment - 1:

Look at the below example, execute & evaluate and check your learning so far 

```js
function myFunction() {
  console.log(x); // undefined
  console.log(y); // ReferenceError: y is not defined
  console.log(z); // ReferenceError: z is not defined
  var x = 1;
  let y = 2;
  const z = 3;
  if (true) {
    var x = 10;
    let y = 20;
    const z = 30;
    console.log(x); // 10
    console.log(y); // 20
    console.log(z); // 30
  }
  console.log(x); // 10
  console.log(y); // 2
  console.log(z); // 3
}
```

## Explanation:

This code defines a function called `myFunction`. Inside the function, it declares three variables using `var`, `let`, and `const`: `x`, `y`, and `z`, respectively. It then logs the values of these variables to the console.

The first three `console.log()` statements will log `undefined`, `ReferenceError: y is not defined`, and `ReferenceError: z is not defined`, respectively. This is because `x` is declared using `var` and has function scope, so it is hoisted to the top of the function and assigned a default value of `undefined` before it is actually declared and assigned the value `1`. `y` and `z`, on the other hand, are declared using `let` and `const`, respectively, and have block scope. They are not hoisted, so attempting to access them before they are declared results in a `ReferenceError`.

Inside the `if` block, `x`, `y`, and `z` are re-declared and assigned new values. Since `var` has function scope, the re-declaration of `x` inside the `if` block also affects the value of `x` outside of the block. `let` and `const`, on the other hand, have block scope, so their re-declaration inside the `if` block only affects their values inside the block.

After the `if` block, the function logs the values of `x`, `y`, and `z` again. This time, `x` has a value of `10` because it was re-declared inside the `if` block. `y` still has a value of `2` because it was not affected by the re-declaration of `y` inside the `if` block, and `z` still has a value of `3` because `const` variables cannot be reassigned.

# Assessment - 2

Read & execute below code & check your learning:

```js
let name = 'Mr. John';

function getInfo() {
  console.log('1. name = ', name);

  var name = "Ms. John";
  return name;
}

console.log("2. name = ", getInfo());
```

## Explained

This code declares a global variable called `name` and assigns it the value `"Mr. John"`. It also defines a function called `getInfo`, which logs the value of a variable called `name` and then re-declares and assigns it the value `"Ms. John"`, before returning the new value of `name`.

When the `getInfo` function is called by the `console.log()` statement outside the function, it first logs the value of `name`. However, inside the function, there is a variable declaration for `name` using the `var` keyword. This creates a new variable with the same name as the global variable `name` but with function scope. 

Since `var` variables are hoisted to the top of the function scope, the variable `name` is actually hoisted to the top of the function, so the first `console.log()` statement inside the function logs `undefined` instead of `"Mr. John"`. Then, the `name` variable is re-declared and assigned the value `"Ms. John"`, which is returned by the function and logged to the console by the outer `console.log()` statement. Therefore, the output of the code will be:

```
1. name =  undefined
2. name =  Ms. John
```

It's important to note that `let` variables are not hoisted like `var` variables, so if `let` was used to declare `name` instead of `var` inside the `getInfo` function, it would have thrown a `ReferenceError` when attempting to access `name` before it was declared.
