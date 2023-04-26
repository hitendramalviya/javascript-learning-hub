# Operators:

JavaScript includes various types of operators, such as arithmetic, assignment, comparison, and logical operators. You'll need to understand how to use these operators to perform various operations on variables and data.

Operators in JavaScript are symbols that are used to perform operations on values or variables. JavaScript includes several types of operators, including:

## Arithmetic Operators:

These operators are used to perform mathematical calculations, such as addition, subtraction, multiplication, division, and modulus. For example:

  ```js
    let x = 10;
    let y = 5;
    let result = x + y; // result = 15
  ```

## Assignment Operators:

These operators are used to assign values to variables. The most common assignment operator is the equals sign (=). For example:

  ```js
  let x = 10;
  x += 5; // equivalent to x = x + 5
  ```

## Comparison Operators:

These operators are used to compare two values or variables and return a boolean value (true or false). Examples of comparison operators include equals (==), not equals (!=), greater than (>), less than (<), and greater than or equal to (>=). For example:

  ```js
  let x = 10;
  let y = 5;
  let result = x > y; // result = true
  ```

## Logical Operators:

These operators are used to combine multiple conditions and return a boolean value. Examples of logical operators include AND (&&), OR (||), and NOT (!). For example:

  ```js
  let x = 10;
  let y = 5;
  let z = 7;
  let result = (x > y) && (y < z); // result = true
  ```

## Unary Operators:

These operators are used to perform operations on a single operand. Examples of unary operators include increment (++), decrement (--), and typeof (typeof x). For example:

  ```js
  let x = 10;
  x++; // x = 11
  ```

Understanding operators is important in JavaScript, as they are used extensively in programming to manipulate and compare values, and to control the flow of your code.

# Assessments

## Assessment - 1

Look at below code & check your learning about operators

```js
let a = '';
let b = null;
let c = 0;

if (a || b || c) {
    console.log('Hello');
}

// expression1 => a => falsy => evaluate to false
// expression2 => b => truthy => evaluate to true

// expression1 || expression2 => true
```

In this code, there is an `if` statement that checks whether the logical OR (`||`) of the variables `a`, `b`, and `c` is truthy or falsy.

The logical OR operator evaluates the expression from left to right and returns the first truthy value it finds, or the last value if all values are falsy. In JavaScript, the following values are considered falsy: `false`, `null`, `undefined`, `0`, `NaN`, and an empty string (`''`).

In this case, `a` is an empty string (`''`), which is a falsy value. `b` is `null`, which is also falsy. `c` is `0`, which is also falsy. Since all three values are falsy, the entire expression evaluates to `false`.

Therefore, the `console.log()` statement inside the `if` block will not be executed, and nothing will be outputted to the console.

## Assessment - 2

```js
// User is filling a form, and we want to validate his/her age should be between 18 & 24 ?
let age = 25;
if (age < 18 || age > 24) {
    console.log('Age criteria does not meet, age must be between 18 & 24!');
}
```

In this code, there is an `if` statement that checks whether the variable `age` is less than 18 or greater than 24, using the logical OR (`||`) operator.

The logical OR operator evaluates the expression from left to right and returns the first truthy value it finds, or the last value if all values are falsy. In JavaScript, any number that is not `0` is considered truthy.

In this case, `age` is `25`, which is greater than 24 and therefore truthy. Therefore, the entire expression evaluates to `true`.

Therefore, the `console.log()` statement inside the `if` block will be executed, and the message "Age criteria does not meet, age must be between 18 & 24!" will be outputted to the console.


## Assessment - 3

```js
let a = '';
let age = 15;
if (a || age < 18) {
    console.log('Age should equal or above 18')
}
```

In this code, there is an `if` statement that checks whether either the variable `a` is truthy or the variable `age` is less than `18`.

The logical OR (`||`) operator evaluates the expression from left to right and returns the first truthy value it finds, or the last value if all values are falsy. In JavaScript, the following values are considered falsy: `false`, `null`, `undefined`, `0`, `NaN`, and an empty string (`''`).

In this case, `a` is an empty string (`''`), which is a falsy value. `age` is `15`, which is less than `18` and therefore truthy. Since one of the two operands (`age`) is truthy, the entire expression evaluates to `true`.

Therefore, the `console.log()` statement inside the `if` block will be executed, and the message "Age should equal or above 18" will be outputted to the console.


## Assessment - 4 (AND)

```js
let a = ''
let b = null;
let c = 'string';

if (a && b && c) {
    console.log('Registration successful!');
}

// exp1 => a => falsy => false
// exp2 => b => falsy => false
// exp3 => c => truthy => true
```

In this code, there is an `if` statement that checks whether all three variables `a`, `b`, and `c` are truthy, using the logical AND (`&&`) operator.

The logical AND operator evaluates the expression from left to right and returns the first falsy value it finds, or the last value if all values are truthy. In JavaScript, the following values are considered falsy: `false`, `null`, `undefined`, `0`, `NaN`, and an empty string (`''`).

In this case, `a` is an empty string (`''`), which is a falsy value. `b` is `null`, which is also falsy. Therefore, the expressions `a && b` evaluates to `false`, and the entire expression `a && b && c` also evaluates to `false`, without even evaluating the last operand `c`.

Therefore, the `console.log()` statement inside the `if` block will not be executed, and nothing will be outputted to the console.

## Assessment - 5 (AND)

```js
// So the code a && b || c && d is essentially the same as if the && expressions were in parentheses: (a && b) || (c && d).
let a = 1, b = 2, c = '', d = 4;

if (a && b || c && d) {
    console.log('True');
}
```

In this code, there is an `if` statement that checks whether either the expressions `a && b` or `c && d` are truthy, using the logical OR (`||`) operator.

The logical AND (`&&`) operator has higher precedence than the logical OR operator. Therefore, the expression `a && b` will be evaluated first. Since both `a` and `b` are non-zero numbers and therefore truthy, the expression `a && b` evaluates to `true`.

Then, the expression `c && d` will be evaluated. Since `c` is an empty string (`''`), which is a falsy value, the expression `c && d` evaluates to `false`.

Finally, the logical OR operator will evaluate the two results `true` and `false`. Since one of the two operands (`a && b`) is truthy, the entire expression evaluates to `true`.

Therefore, the variable `c` will not be assigned a value and nothing will be outputted to the console.

## Assessment - 6 (NOT)

```js
// NOT (!)
// Problem statement: Validate the form field name & age, both are required field, also age should be grater than 18
// Expected output: It should print the message if above validation fail.
let name = '';
let age = 15;
if (!name || !age || age < 18) {
    console.log('Name & age are required input! and age should be grater than 18!');
}
```

In this code, there is an `if` statement that checks whether the variables `name` and `age` are truthy, and whether the value of `age` is less than `18`.

The logical NOT (`!`) operator is used to negate the truthiness of the operands. It returns `true` if the operand is falsy, and `false` if the operand is truthy.

In this case, `name` is an empty string (`''`), which is a falsy value. Therefore, `!name` evaluates to `true`. `age` is `15`, which is a truthy value. Therefore, `!age` evaluates to `false`. Also, `age` is less than `18`, so `age < 18` is also true.

Therefore, the entire expression `!name || !age || age < 18` evaluates to `true`. As a result, the `console.log()` statement inside the `if` block will be executed, and the message "Name & age are required input! and age should be grater than 18!" will be outputted to the console.


## Assessment - 7 (NOT)

```js
let a = 1, b = '1';

if (a !== b) {
    console.log('Not equal');
}
```

In this code, the `if` statement checks if the value of variable `a` is not equal to the value of variable `b`.

The `!==` operator is the strict not equal operator in JavaScript, which checks the equality of two values, but without performing type coercion. It returns `true` if the values are not equal, both in terms of their value and type.

In this case, `a` is a number (`1`) and `b` is a string (`'1'`). Although both values have the same value, they have different types. Therefore, the expression `a !== b` evaluates to `true`, because they are not strictly equal.

Therefore, the `console.log()` statement inside the `if` block will be executed, and the message "Not equal" will be outputted to the console.

# Takeaways

The `==` and `===` operators are used to compare values in JavaScript, but they differ in terms of how they perform type coercion and comparison.

The `==` operator performs type coercion if the operands are of different types, before comparing their values. It converts the operands to a common type and then compares their values. For example, if we compare the string `"1"` and the number `1` using the `==` operator, it will convert the string to a number and then compare the two values. In this case, the comparison would be true because both values are equal numerically.

The `===` operator, on the other hand, performs a strict comparison without any type coercion. It compares both the values and their types. For example, if we compare the string `"1"` and the number `1` using the `===` operator, it will return false because they are of different types.

In summary, the `==` operator checks if the values are equal after performing type coercion if necessary, while the `===` operator checks if the values are equal and of the same type, without performing any type coercion. 

It is generally recommended to use the `===` operator for strict equality checks, as it helps avoid unexpected behavior that can occur with the `==` operator.


