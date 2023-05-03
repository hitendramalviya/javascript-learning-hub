# Control flow

Control flow refers to the order in which statements are executed in a program. In JavaScript, the flow of control is determined by conditional statements (`if`, `else if`, `else`), loops (`for`, `while`, `do while`), and function calls.

Conditional statements allow you to execute a block of code if a certain condition is met. Here's an example of an `if` statement:

```js
if (x > 0) {
  console.log("x is positive");
} else if (x < 0) {
  console.log("x is negative");
} else {
  console.log("x is zero");
}
```

In this example, the code inside the `if` block will be executed if `x` is greater than 0, the code inside the `else if` block will be executed if `x` is less than 0, and the code inside the `else` block will be executed if `x` is equal to 0.


## Switch-Case


The `switch` statement allows you to execute a block of code based on the value of an expression. Here's an example:

```js
switch (fruit) {
  case "banana":
    console.log("The fruit is a banana.");
    break;
  case "apple":
    console.log("The fruit is an apple.");
    break;
  case "orange":
    console.log("The fruit is an orange.");
    break;
  default:
    console.log("I don't know what fruit that is.");
}
```

In this example, the value of the `fruit` variable is compared to each `case` statement. If the value matches a `case`, the code block associated with that `case` is executed. If none of the `case` values match, the `default` code block is executed.

Like other control flow statements, the `switch` statement can be used to make decisions in your code based on certain conditions, allowing your program to execute different blocks of code based on those conditions.

## Choosing between if else if, else & switch case

Choosing between `if-else` and `switch` statements in JavaScript depends on the specific situation and personal preference. Here are some factors to consider:

1. Complexity: If you have many conditions to evaluate or complex conditions that require multiple logical operators, `if-else` statements can be more readable and easier to maintain than a `switch` statement with multiple `case` statements.

2. Type of comparison: `if-else` statements can perform more complex comparisons than `switch` statements. For example, you can compare strings using `if-else` statements using string methods like `includes()` or `indexOf()`, whereas `switch` statements only support strict equality comparison (`===`).

3. Performance: In some cases, `switch` statements can be faster than `if-else` statements, especially when comparing against a large number of conditions. However, modern JavaScript engines can optimize both statements, so this difference is often negligible.

4. Personal preference: Ultimately, choosing between `if-else` and `switch` statements comes down to personal preference and coding style. Some developers prefer the readability and simplicity of `if-else` statements, while others prefer the structure and organization of `switch` statements.

In general, `if-else` statements are more flexible and can handle more complex conditions, while `switch` statements are more concise and organized for simple conditions. Choose the statement that makes the most sense for your specific situation and coding style.


```js
let employmentType = ''; // Permanent, Contract, Temporary

// Approach 1
if (employmentType === 'Permanent') {

} else if (employmentType === 'Contract') {

} else if (employmentType === 'Temporary') {

}

// Approach 2
if (employmentType === 'Permanent') {

}

if (employmentType === 'Contract') {

}

if (employmentType === 'Temporary') {

}


// Approach 3

switch (employmentType) {
  case 'Permanent':
    {
      // Block for permanent emp
      break;
    }
  case 'Contract':
    {
      // Block for contract emp
      break;
    }
  case 'Temporary':
    {
      // Block for temp emp
      break;
    }
  default:
    {
      throw new Error('Invalid employmentType!');
    }
}
```