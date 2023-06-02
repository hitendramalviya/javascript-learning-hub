# Object

In JavaScript, an object is a fundamental data type that allows you to store and organize related data and functions together. It is a collection of key-value pairs, where each key is a unique identifier (also known as a property or member), and each value can be any data type, including other objects.

Here's an explanation of objects in JavaScript:

1. Object Declaration:
   - Objects can be declared using object literal notation, which involves enclosing key-value pairs within curly braces `{}`.
   - Each key-value pair consists of a property name (key) and its associated value, separated by a colon `:`.
   - Multiple key-value pairs are separated by commas `,`.

   Example:
   ```javascript
   const person = {
     name: 'John',
     age: 30,
     email: 'john@example.com'
   };
   ```

2. Accessing Object Properties:
   - You can access the properties of an object using dot notation (`objectName.propertyName`) or bracket notation (`objectName['propertyName']`).
   - Dot notation is commonly used when the property name is known in advance, while bracket notation is useful when the property name is dynamic or contains special characters.

   Example:
   ```javascript
   console.log(person.name); // Output: John
   console.log(person['age']); // Output: 30
   ```

3. Modifying Object Properties:
   - You can modify the value of an object property by assigning a new value using the assignment operator (`=`).
   - The property name remains the same, and only the value is updated.

   Example:
   ```javascript
   person.age = 31;
   console.log(person.age); // Output: 31
   ```

4. Adding and Removing Object Properties:
   - You can add new properties to an object by assigning a value to a non-existent property.
   - Similarly, you can remove a property from an object using the `delete` keyword followed by the property name.

   Example:
   ```javascript
   person.location = 'London';
   console.log(person.location); // Output: London

   delete person.email;
   console.log(person.email); // Output: undefined
   ```

5. Object Methods:
   - In addition to storing data, objects in JavaScript can also contain functions, which are called methods.
   - These methods can be defined as properties with function expressions or function declarations.

   Example:
   ```javascript
   const person = {
     name: 'John',
     age: 30,
     sayHello: function() {
       console.log('Hello!');
     }
   };

   person.sayHello(); // Output: Hello!
   ```

Objects are versatile and widely used in JavaScript. They provide a powerful way to organize and manipulate data, making them a fundamental part of JavaScript programming.


## Object reference

In JavaScript, when you assign an object to a variable or pass an object as a function argument, you are actually creating a reference to that object. This means that the variable doesn't store the object itself, but rather a reference to the location in memory where the object is stored. Understanding object references is crucial when working with objects in JavaScript.

Here are some important points to understand about object references:

1. Reference Assignment:
   - When you assign an object to a variable, the variable holds a reference to the object's location in memory. It doesn't create a new copy of the object.
   - If you assign the object to another variable, both variables will reference the same object.

   Example:
   ```javascript
   const obj1 = { name: 'John' };
   const obj2 = obj1; // obj2 now references the same object as obj1

   console.log(obj1 === obj2); // Output: true
   ```

2. Modifying Object Properties:
   - Since variables holding objects reference the same object, modifying the object through one variable will affect all variables referencing the object.
   - This is because they all point to the same memory location.

   Example:
   ```javascript
   const person = { name: 'John' };
   const alias = person;

   person.name = 'Jane';

   console.log(alias.name); // Output: Jane
   ```

3. Pass by Reference:
   - When passing an object as a function argument, the reference to the object is passed, not a copy of the object.
   - If you modify the object within the function, the changes will be reflected outside the function.

   Example:
   ```javascript
   function updateName(obj) {
     obj.name = 'Jane';
   }

   const person = { name: 'John' };
   updateName(person);

   console.log(person.name); // Output: Jane
   ```

4. Comparison of Object References:
   - When comparing objects using comparison operators like `===` or `==`, they are compared by reference.
   - Two objects are considered equal only if they reference the same object in memory.

   Example:
   ```javascript
   const obj1 = { name: 'John' };
   const obj2 = { name: 'John' };

   console.log(obj1 === obj2); // Output: false
   ```

Understanding object references is important to avoid unexpected behavior and to work effectively with objects in JavaScript. It allows you to manipulate and share data efficiently by working with the same underlying object through different references.

## Object prototype

When we create an object using the `Object.create` method, each object is linked to `Object.prototype`, allowing the prototype object to inherit properties from other objects. Although we will delve into functions in the next chapter, you can have a glimpse of it below. We have created a custom `Object.create` function to visualize the prototype:

```javascript
if (typeof Object.create !== 'function') {
  Object.create = function (o) {
    var F = function () {};
    F.prototype = o;
    return new F();
  }
}

var obj = Object.create({ firstName: 'John', lastName: 'Jacob' });
```

When we make updates to the object, it does not affect its prototype; the prototype remains unchanged and is only used for property retrieval. When we try to access a property value from an object and the object itself does not contain that property, JavaScript looks into the prototype object. If the property is still not found, it continues to traverse up the prototype chain until it reaches `Object.prototype`. If the desired property is not found at any level, it will return `undefined`. This behavior is known as *delegation*.

To see this behavior in action, we will demonstrate it with the following code. However, please note that we are using the internal private property `__proto__`, which is not recommended for use in real-time code.

```javascript
obj.firstName = 'Test';
console.log(obj.firstName); // It will print 'Test'
console.log(obj.__proto__.firstName); // It will print 'John' (NOT RECOMMENDED TO BE USED __proto__ in REAL TIME)
console.log(obj.middleName); // It will print undefined, as the property does not exist in the prototype chain until Object.prototype.
```


# Reflection

In JavaScript, reflection refers to the ability to examine and modify the properties and methods of an object at runtime. It allows you to dynamically inspect and manipulate objects, gaining insights into their structure and behavior. Reflection in JavaScript is primarily achieved through the use of built-in methods and features.

Here are some key aspects of reflection in JavaScript:

1. Property Inspection:
   - You can inspect an object's properties using methods like `Object.keys()`, `Object.getOwnPropertyNames()`, and `for...in` loop.
   - These methods allow you to retrieve information about an object's own properties, including enumerable and non-enumerable properties.

   Certainly! Here's an example demonstrating property inspection using `Object.keys()` and `for...in` loop:

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30,
  email: 'johndoe@example.com'
};

// Using Object.keys()
const keys = Object.keys(person);
console.log(keys); // Output: ['firstName', 'lastName', 'age', 'email']

// Using for...in loop
for (let key in person) {
  console.log(key); // Output: firstName, lastName, age, email
}
```

In the above code, we have an object `person` with several properties. We use `Object.keys()` to retrieve an array of all the own enumerable properties of the `person` object. This array contains the property names `firstName`, `lastName`, `age`, and `email`. 

Additionally, we utilize a `for...in` loop to iterate over all the enumerable properties of the `person` object, this is also known as *Enumeration*. Inside the loop, we log each property name (`key`) to the console. In this example, the loop will output the same property names as `Object.keys()`.

These techniques allow you to inspect the properties of an object dynamically, providing insight into its structure and allowing you to perform operations based on the available properties.

2. Property Access and Modification:
   - With reflection, you can access and modify an object's properties dynamically using bracket notation (`[]`) or the `.` dot operator.
   - This enables you to retrieve the value of a property, set a new value, or even delete a property from an object.

   Certainly! Here's an example demonstrating property access and modification dynamically:

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30,
  email: 'johndoe@example.com'
};

// Property Access
console.log(person.firstName); // Output: John
console.log(person['lastName']); // Output: Doe

// Property Modification
person.age = 35;
person['email'] = 'john.doe@example.com';

console.log(person.age); // Output: 35
console.log(person['email']); // Output: john.doe@example.com
```

In the above code, we have an object `person` with several properties such as `firstName`, `lastName`, `age`, and `email`.

To access the property values, we can use either dot notation (`object.propertyName`) or bracket notation (`object['propertyName']`). In the example, we access the `firstName` property using dot notation (`person.firstName`) and the `lastName` property using bracket notation (`person['lastName']`).

For property modification, we simply assign a new value to the desired property. In the example, we update the `age` property to `35` and the `email` property to `'john.doe@example.com'`.

By using property access and modification dynamically, you can work with object properties based on runtime conditions or user input, allowing your code to be more flexible and adaptable.

3. Method Invocation:
   - Reflection allows you to invoke object methods dynamically.
   - You can use the `call()` or `apply()` methods to call a method with a specific context and arguments.
   - These methods allow you to dynamically choose the object on which the method should be called.

   Example for call & apply we delve into functions chapter.

4. Checking Property Existence:
   - Reflection provides methods to check if a property exists in an object.
   - The `hasOwnProperty()` method checks if an object has its own property, while the `in` operator checks if a property exists anywhere in the object's prototype chain.

   Certainly! Here's an example demonstrating checking property existence using `hasOwnProperty()` and the `in` operator:

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30
};

console.log(person.hasOwnProperty('firstName')); // Output: true
console.log(person.hasOwnProperty('middleName')); // Output: false

console.log('age' in person); // Output: true
console.log('email' in person); // Output: false
```

In the above code, we have an object `person` with properties like `firstName`, `lastName`, and `age`.

To check if an object has its own property, we can use the `hasOwnProperty()` method. It returns `true` if the object has the specified property as its own property, and `false` otherwise. In the example, we check if `person` has the properties `'firstName'` and `'middleName'` using `hasOwnProperty()`. The output is `true` for `'firstName'` and `false` for `'middleName'`.

The `in` operator is another way to check for the existence of a property in an object. It returns `true` if the property exists anywhere in the object's prototype chain, including both own properties and inherited properties. In the example, we use the `in` operator to check if `'age'` and `'email'` properties exist in `person`. The output is `true` for `'age'` and `false` for `'email'`.

These techniques allow you to dynamically check the existence of properties in an object, which can be useful for conditionally handling different scenarios or performing specific actions based on the presence or absence of certain properties.

5. Dynamic Property Creation and Deletion:
   - Reflection enables you to dynamically add or remove properties from an object.
   - You can use assignment (`=`) to create new properties or the `delete` keyword to remove existing properties.

   Certainly! Here's an example demonstrating dynamic property creation and deletion:

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30
};

// Dynamic Property Creation
person.middleName = 'Robert';
person['email'] = 'john.doe@example.com';

console.log(person.middleName); // Output: Robert
console.log(person['email']); // Output: john.doe@example.com

// Dynamic Property Deletion
delete person.age;
delete person['lastName'];

console.log(person.age); // Output: undefined
console.log(person['lastName']); // Output: undefined
```

In the above code, we have an object `person` with initial properties such as `firstName`, `lastName`, and `age`.

To dynamically create a new property, you can simply assign a value to a non-existent property using either dot notation or bracket notation. In the example, we add the `middleName` property with the value `'Robert'` using dot notation (`person.middleName`) and the `email` property with the value `'john.doe@example.com'` using bracket notation (`person['email']`).

To dynamically delete a property from an object, you can use the `delete` keyword followed by the object name and the property name as either dot notation or bracket notation. In the example, we delete the `age` property using `delete person.age` and the `lastName` property using `delete person['lastName']`.

After the creation or deletion of properties, accessing those properties will return `undefined` since they no longer exist in the object.

Dynamic property creation and deletion can be useful when you need to modify an object's structure based on runtime conditions or dynamically adjust the object's properties during program execution.

Reflection in JavaScript gives you the flexibility to examine and manipulate objects dynamically. It is commonly used in scenarios where you need to perform operations based on the runtime structure of objects, such as creating generic functions or implementing dynamic behavior in frameworks and libraries. However, it's important to use reflection judiciously and be aware of the performance implications it may have on your code.

## Understand Globals in JavaScript

Global variables refer to variables that are declared outside of any function or block scope in JavaScript. They have global scope and can be accessed from anywhere in the code. While global variables may seem convenient, they can indeed weaken the resiliency of programs and should generally be avoided. Here's an explanation with an example:

1. Name conflicts: When using global variables, there is a higher risk of encountering name conflicts. Since global variables are accessible from anywhere, if multiple parts of your codebase use the same variable name, it can lead to unintended consequences and errors. This can make the codebase harder to maintain and debug. Consider the following example:

```javascript
// Global variable
let count = 0;

function incrementCount() {
  count++;
}

function resetCount() {
  count = 0;
}

incrementCount();
console.log(count); // Output: 1

resetCount();
console.log(count); // Output: 0

// Unexpected interference if another part of the code also uses 'count'
```

2. Implicit dependencies: Global variables create implicit dependencies between different parts of your code. When a variable can be accessed and modified from anywhere, it becomes challenging to track its usage and determine which parts of the code rely on it. This can lead to code that is harder to understand, test, and maintain.

3. Debugging and testing difficulties: Global variables can make debugging and testing more challenging. Since they can be modified from anywhere, it becomes harder to isolate and reproduce specific scenarios. It can also result in unexpected behavior or side effects when trying to test different parts of the code independently.

To address these issues, it is generally recommended to limit the use of global variables and instead use local variables within functions or modules. By encapsulating variables within specific scopes, you reduce the risk of name conflicts, make dependencies explicit, and improve the maintainability and testability of your code.

By following best practices, such as using function parameters and return values, modules, and proper scoping, you can minimize the reliance on global variables and create more resilient and manageable programs.

Certainly! Here's an example demonstrating how you can use an object to avoid unnecessary global variables:

```javascript
// Using an object to avoid unnecessary globals
const myApp = {
  count: 0,

  incrementCount() {
    this.count++;
  },

  resetCount() {
    this.count = 0;
  }
};

myApp.incrementCount();
console.log(myApp.count); // Output: 1

myApp.resetCount();
console.log(myApp.count); // Output: 0
```

In the above example, instead of using a global variable directly, we encapsulate our data and functions within the `myApp` object. The `count` property is stored as a property of the `myApp` object.

By organizing our variables and functions within this object, we avoid cluttering the global scope and minimize the risk of name conflicts with other parts of the code. The properties and methods of the `myApp` object can only be accessed using `myApp.propertyName` or `myApp.methodName`.

This approach promotes better encapsulation and separation of concerns. It makes the dependencies explicit and allows for better control and management of the variables and functions within the object.

By adopting this pattern, you can create more modular and maintainable code, reduce the risk of naming conflicts, and improve the overall resiliency of your program.