# Control flow

Control flow refers to the order in which statements are executed in a program, JavaScript uses various control flow statements to determine the order in which code is executed based on different conditions. In JavaScript, the flow of control is determined by conditional statements (`if`, `else if`, `else`), loops (`for`, `while`, `do while`), and function calls.


1. If-else Statements: If-else statements are used to execute code blocks based on a condition. If the condition is true, the code inside the if block is executed, otherwise, the code inside the else block is executed. 

The if-else statement in JavaScript is used to execute a block of code based on a condition. The syntax for an if-else statement is as follows:

```js
if (condition) {
  // code to execute if condition is true
} else {
  // code to execute if condition is false
}
```

Here's an example of an if-else statement in action:

```js
let age = 18;

if (age >= 18) {
  console.log("You are old enough to vote");
} else {
  console.log("You are not old enough to vote");
}
```

In this example, the condition is `age >= 18`. If the age is greater than or equal to 18, the code inside the first block is executed which prints "You are old enough to vote" to the console. Otherwise, the code inside the second block is executed which prints "You are not old enough to vote" to the console.

If-else statements are often used to perform different actions based on user input or to validate input data in web forms. They can also be nested within each other to create more complex conditions and code blocks.

2. While Loop: A while loop is used to repeatedly execute a block of code while a condition is true.

The while loop is a control flow statement in JavaScript that allows you to execute a block of code repeatedly as long as a certain condition is true. The general syntax of a while loop is as follows:

```js
while (condition) {
  // code to be executed while the condition is true
}
```

Here, `condition` is the boolean expression that you want to evaluate. The code inside the curly braces will continue to execute repeatedly as long as the condition is true. The condition is evaluated before each iteration of the loop, so if the condition is initially false, the code inside the loop will never be executed.

Here's an example of a while loop that counts from 1 to 5:

```js
let i = 1;
while (i <= 5) {
  console.log(i);
  i++;
}
```

In this example, the variable `i` is initially set to 1. The while loop then checks if `i` is less than or equal to 5. Since this condition is true, the code inside the loop is executed, which logs the value of `i` to the console and then increments `i` by 1. This process continues until `i` is no longer less than or equal to 5, at which point the loop exits.

While loops can be useful for cases where you want to execute a block of code a specific number of times or until a certain condition is met. However, it's important to ensure that the condition will eventually become false, otherwise you risk creating an infinite loop that will continue to execute indefinitely. Additionally, you should make sure that the loop has an exit condition that will allow it to terminate even if the desired condition is never met.

3. For Loop: A for loop is used to repeatedly execute a block of code for a fixed number of times.

The for loop is a control flow statement in JavaScript that allows you to execute a block of code repeatedly for a specific number of times. The general syntax of a for loop is as follows:

```js
for (initialization; condition; update) {
  // code to be executed repeatedly
}
```

Here, `initialization` is an expression that initializes a counter variable or any other variable that you want to use in the loop. `condition` is a boolean expression that is evaluated before each iteration of the loop, and the loop will continue to execute as long as this condition is true. `update` is an expression that is executed at the end of each iteration of the loop, and is typically used to update the value of the counter variable.

Here's an example of a for loop that counts from 1 to 5:

```js
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

In this example, the counter variable `i` is initialized to 1, and the loop will continue to execute as long as `i` is less than or equal to 5. The code inside the loop logs the value of `i` to the console, and then increments `i` by 1 at the end of each iteration. Once `i` is no longer less than or equal to 5, the loop exits.

For loops can be useful for cases where you need to iterate over a fixed number of items, such as the elements of an array. You can use the counter variable to access each element of the array, and perform some operation on it. Additionally, you can use the `break` and `continue` statements to control the flow of the loop and exit early if necessary.

It's important to note that for loops can also be used to iterate over objects, although the syntax is slightly different. In this case, you would use a `for...in` loop, which will iterate over each property of the object.

4. Switch Statement: A switch statement is used to execute different code blocks based on different conditions.

The switch statement in JavaScript is another way to control the flow of code based on a specific value. It's used when you have a variable that you want to compare against multiple possible values, and execute different code blocks depending on which value the variable matches. The syntax for a switch statement is as follows:

```js
switch (expression) {
  case value1:
    // code to execute if expression matches value1
    break;
  case value2:
    // code to execute if expression matches value2
    break;
  ...
  default:
    // code to execute if expression doesn't match any of the values
}
```

Here's an example of a switch statement in action:

```js
let day = "Tuesday";

switch (day) {
  case "Monday":
    console.log("It's Monday!");
    break;
  case "Tuesday":
    console.log("It's Tuesday!");
    break;
  case "Wednesday":
    console.log("It's Wednesday!");
    break;
  default:
    console.log("It's some other day!");
}
```

In this example, the variable `day` is compared to different possible values using the switch statement. Since the value of `day` is "Tuesday", the code inside the second block is executed which prints "It's Tuesday!" to the console. If `day` had been "Monday" or "Wednesday", the code inside the corresponding block would have been executed instead. If `day` had been any other value, the code inside the default block would have been executed.

Switch statements can be useful for cases where you have a lot of possible values to compare against, as they can be more concise than writing multiple if-else statements. However, they can be less flexible than if-else statements since they can only compare against specific values, not ranges or conditions.


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


## Ternary operator

The ternary operator is another way to control the flow of code in JavaScript, specifically for simple if-else statements. It's used when you have a single condition that you want to check, and execute one block of code if the condition is true, and another block of code if the condition is false. The syntax for the ternary operator is as follows:

```js
condition ? expression1 : expression2
```

Here, `condition` is the boolean expression that you want to evaluate, and `expression1` and `expression2` are the values or expressions that you want to return based on whether the condition is true or false, respectively.

Here's an example of the ternary operator in action:

```js
let age = 18;
let message = age >= 18 ? "You're an adult" : "You're a minor";
console.log(message);
```

In this example, the ternary operator is used to check whether the variable `age` is greater than or equal to 18. If it is, the expression "You're an adult" is returned and assigned to the variable `message`. If it's not, the expression "You're a minor" is returned instead. In this case, since `age` is equal to 18, the first expression is returned and `message` is set to "You're an adult". The code then logs this message to the console.

The ternary operator can be useful for cases where you have a simple if-else statement with only two possible outcomes, as it can be more concise than writing out the full if-else block. However, it can become less readable for more complex conditions, and it's important to ensure that the code remains clear and understandable to other developers.

## Continue & Break the loop


In JavaScript, `continue` and `break` are used in loops to control the flow of the loop.

`continue` is used to skip the current iteration of a loop and move on to the next iteration. When the `continue` statement is encountered inside a loop, the rest of the statements in the loop block are skipped for the current iteration and the loop proceeds to the next iteration.

Here's an example of how `continue` works in a `for` loop:

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    continue;
  }
  console.log(i);
}
```

In this example, when `i` is equal to 3, the `continue` statement is executed, which skips the rest of the statements in the loop block and proceeds to the next iteration. As a result, the number 3 is skipped in the output.

`break` is used to exit a loop early. When the `break` statement is encountered inside a loop, the loop is terminated and the program continues with the next statement outside the loop.

Here's an example of how `break` works in a `while` loop:

```js
let i = 1;
while (i <= 5) {
  console.log(i);
  if (i === 3) {
    break;
  }
  i++;
}
```

In this example, when `i` is equal to 3, the `break` statement is executed, which terminates the `while` loop early. As a result, the output only includes the numbers 1, 2, and 3.

Both `continue` and `break` are powerful tools for controlling the flow of loops in JavaScript and can be used to create more complex logic for your programs.

Here is another example

```js
// Define an array of numbers
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// Initialize a sum variable to 0
let sum = 0;

// Use a for loop to iterate over the array and sum the values
for (let i = 0; i < numbers.length; i++) {
  // If the current number is even, skip it
  if (numbers[i] % 2 === 0) {
    continue;
  }

  // If the current number is greater than 5, exit the loop
  if (numbers[i] > 5) {
    break;
  }

  // Add the current number to the sum
  sum += numbers[i];
}

// Log the final sum to the console
console.log(sum);
```

In this example, we start by defining an array of numbers. We then initialize a variable `sum` to 0.

We use a `for` loop to iterate over the array of numbers. For each number, we check if it is even using an `if` statement. If the number is even, we skip it using the `continue` statement.

We then check if the number is greater than 5. If it is, we exit the loop early using the `break` statement.

If neither of these conditions is true, we add the current number to the `sum` variable.

Finally, we log the final value of `sum` to the console.

This code exercise demonstrates the use of a `for` loop, `if` statements with `continue` and `break` statements to control the flow of the loop, and arithmetic operations to calculate a final result.

# Functions

# Object