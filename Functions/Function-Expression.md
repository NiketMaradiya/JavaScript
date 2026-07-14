# JavaScript Function Expression

## What is a Function Expression?

A **Function Expression** means creating a function and storing it inside a variable.

```javascript
const greet = function () {
  console.log("Hello!");
};
```

To execute the function:

```javascript
greet();
```

Output:

```text
Hello!
```

---

# Basic Syntax

```javascript
const variableName = function () {
  // Function code
};
```

Example:

```javascript
const showMessage = function () {
  console.log("Welcome to JavaScript");
};

showMessage();
```

Output:

```text
Welcome to JavaScript
```

---

# Function Expression with Parameters

Parameters receive values when the function is called.

```javascript
const greetUser = function (name) {
  console.log("Hello, " + name);
};

greetUser("Niket");
greetUser("Rahul");
```

Output:

```text
Hello, Niket
Hello, Rahul
```

Here:

```javascript
name
```

is a parameter.

```javascript
"Niket"
```

is an argument.

---

# Function Expression with Return Value

The `return` keyword sends a result back from the function.

```javascript
const add = function (number1, number2) {
  return number1 + number2;
};

const result = add(10, 20);

console.log(result);
```

Output:

```text
30
```

---

# Anonymous Function Expression

A function without its own name is called an anonymous function.

```javascript
const greet = function () {
  console.log("Good morning");
};

greet();
```

Output:

```text
Good morning
```

The function does not have a name, but it is called using the variable name `greet`.

---

# Named Function Expression

A Function Expression can also have an internal name.

```javascript
const greet = function showGreeting() {
  console.log("Hello!");
};

greet();
```

Output:

```text
Hello!
```

Here:

* `greet` is the variable name.
* `showGreeting` is the internal function name.

You normally call it using:

```javascript
greet();
```

Trying to call the internal name outside causes an error:

```javascript
showGreeting();
```

Error:

```text
ReferenceError: showGreeting is not defined
```

---

# Function Expression with If/Else

```javascript
const checkAge = function (age) {
  if (age >= 18) {
    return "You are eligible to vote";
  } else {
    return "You are not eligible to vote";
  }
};

console.log(checkAge(20));
console.log(checkAge(15));
```

Output:

```text
You are eligible to vote
You are not eligible to vote
```

---

# Function Expression with Multiple Parameters

```javascript
const calculateTotal = function (price, quantity) {
  return price * quantity;
};

console.log(calculateTotal(100, 5));
```

Output:

```text
500
```

---

# Storing a Function in Another Variable

Functions are values in JavaScript.

```javascript
const greet = function () {
  console.log("Hello Niket");
};

const newGreet = greet;

newGreet();
```

Output:

```text
Hello Niket
```

Both variables now reference the same function.

```javascript
greet();
newGreet();
```

Output:

```text
Hello Niket
Hello Niket
```

---

# Passing a Function as an Argument

A function can be passed to another function.

```javascript
const greet = function () {
  console.log("Hello from greet function");
};

const executeFunction = function (callback) {
  callback();
};

executeFunction(greet);
```

Output:

```text
Hello from greet function
```

Use:

```javascript
executeFunction(greet);
```

This passes the function.

Do not use:

```javascript
executeFunction(greet());
```

This executes the function immediately.

---

# Function Expression with setTimeout

```javascript
setTimeout(function () {
  console.log("This message appears after 2 seconds");
}, 2000);
```

The anonymous function runs after approximately two seconds.

---

# Function Expression with Array Method

```javascript
const numbers = [1, 2, 3, 4, 5];

const doubledNumbers = numbers.map(function (number) {
  return number * 2;
});

console.log(doubledNumbers);
```

Output:

```text
[2, 4, 6, 8, 10]
```

---

# Function Declaration vs Function Expression

## Function Declaration

```javascript
function add(number1, number2) {
  return number1 + number2;
}
```

## Function Expression

```javascript
const add = function (number1, number2) {
  return number1 + number2;
};
```

Both are called similarly:

```javascript
console.log(add(10, 20));
```

The main difference is hoisting.

---

# Hoisting Difference

## Function Declaration

A Function Declaration can be called before it is written.

```javascript
greet();

function greet() {
  console.log("Hello");
}
```

Output:

```text
Hello
```

## Function Expression

A Function Expression cannot be called before initialization.

```javascript
greet();

const greet = function () {
  console.log("Hello");
};
```

Error:

```text
ReferenceError: Cannot access 'greet' before initialization
```

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};

greet();
```

---

# Function Expression with let

```javascript
let greet = function () {
  console.log("Good morning");
};

greet();
```

A function stored using `let` can be changed later.

```javascript
let greet = function () {
  console.log("Good morning");
};

greet();

greet = function () {
  console.log("Good evening");
};

greet();
```

Output:

```text
Good morning
Good evening
```

Use `const` when you do not want the function variable to change.

---

# Common Errors

## Error 1: Calling Before Initialization

Wrong:

```javascript
sayHello();

const sayHello = function () {
  console.log("Hello");
};
```

Error:

```text
ReferenceError: Cannot access 'sayHello' before initialization
```

Correct:

```javascript
const sayHello = function () {
  console.log("Hello");
};

sayHello();
```

---

## Error 2: Forgetting Parentheses

```javascript
const greet = function () {
  console.log("Hello");
};

console.log(greet);
```

This displays the function but does not execute it.

Correct:

```javascript
greet();
```

Remember:

```javascript
greet
```

means the function value.

```javascript
greet()
```

means execute the function.

---

## Error 3: Calling a Non-Function Value

```javascript
const greet = "Hello";

greet();
```

Error:

```text
TypeError: greet is not a function
```

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};

greet();
```

---

## Error 4: Missing Assignment Operator

Wrong:

```javascript
const greet function () {
  console.log("Hello");
};
```

Error:

```text
SyntaxError: Missing initializer in const declaration
```

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};
```

---

## Error 5: Missing Curly Braces

Wrong:

```javascript
const greet = function ()
  console.log("Hello");
};
```

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};
```

---

## Error 6: Incorrect Function Keyword

Wrong:

```javascript
const greet = Function () {
  console.log("Hello");
};
```

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};
```

JavaScript is case-sensitive.

---

## Error 7: Calling Internal Function Name Outside

```javascript
const calculate = function addNumbers(a, b) {
  return a + b;
};

console.log(addNumbers(10, 20));
```

Error:

```text
ReferenceError: addNumbers is not defined
```

Correct:

```javascript
console.log(calculate(10, 20));
```

Output:

```text
30
```

---

## Error 8: Missing Argument

```javascript
const add = function (a, b) {
  return a + b;
};

console.log(add(10));
```

Output:

```text
NaN
```

Because:

```text
a = 10
b = undefined
```

Correct:

```javascript
console.log(add(10, 20));
```

Output:

```text
30
```

You can also use a default value:

```javascript
const add = function (a, b = 0) {
  return a + b;
};

console.log(add(10));
```

Output:

```text
10
```

---

## Error 9: Forgetting return

```javascript
const add = function (a, b) {
  a + b;
};

console.log(add(10, 20));
```

Output:

```text
undefined
```

Correct:

```javascript
const add = function (a, b) {
  return a + b;
};

console.log(add(10, 20));
```

Output:

```text
30
```

---

## Error 10: Code After return

```javascript
const test = function () {
  return "Completed";

  console.log("This will not run");
};

console.log(test());
```

Output:

```text
Completed
```

Code after `return` does not execute.

Correct:

```javascript
const test = function () {
  console.log("Function is running");

  return "Completed";
};

console.log(test());
```

---

## Error 11: Replacing Function with Another Value

```javascript
let greet = function () {
  console.log("Hello");
};

greet = 100;

greet();
```

Error:

```text
TypeError: greet is not a function
```

Use `const` to prevent accidental reassignment.

```javascript
const greet = function () {
  console.log("Hello");
};
```

---

## Error 12: Mixing Normal and Arrow Function Syntax

Wrong:

```javascript
const add = function (a, b) => {
  return a + b;
};
```

Correct normal Function Expression:

```javascript
const add = function (a, b) {
  return a + b;
};
```

Correct arrow function:

```javascript
const add = (a, b) => {
  return a + b;
};
```

---

# Practical Example: Student Result

```javascript
const calculateResult = function (marks) {
  if (marks < 0 || marks > 100) {
    return "Invalid marks";
  }

  if (marks >= 90) {
    return "Grade A";
  } else if (marks >= 75) {
    return "Grade B";
  } else if (marks >= 50) {
    return "Grade C";
  } else {
    return "Fail";
  }
};

console.log(calculateResult(95));
console.log(calculateResult(80));
console.log(calculateResult(60));
console.log(calculateResult(30));
console.log(calculateResult(120));
```

Output:

```text
Grade A
Grade B
Grade C
Fail
Invalid marks
```

---

# Practical Example: Simple Calculator

```javascript
const calculator = function (number1, number2, operator) {
  if (operator === "+") {
    return number1 + number2;
  } else if (operator === "-") {
    return number1 - number2;
  } else if (operator === "*") {
    return number1 * number2;
  } else if (operator === "/") {
    if (number2 === 0) {
      return "Cannot divide by zero";
    }

    return number1 / number2;
  } else {
    return "Invalid operator";
  }
};

console.log(calculator(10, 5, "+"));
console.log(calculator(10, 5, "-"));
console.log(calculator(10, 5, "*"));
console.log(calculator(10, 5, "/"));
console.log(calculator(10, 0, "/"));
```

Output:

```text
15
5
50
2
Cannot divide by zero
```

---

# Important Points

* A Function Expression stores a function inside a variable.
* It can be anonymous or named.
* It can accept parameters.
* It can return values.
* It cannot be called before initialization.
* `functionName` refers to the function.
* `functionName()` executes the function.
* Use `const` when the function should not change.
* Function Expressions are commonly used as callbacks.
* Forgetting `return` gives `undefined`.
* Calling a non-function value gives `TypeError`.

---

# Final Example

```javascript
const multiply = function (a, b) {
  return a * b;
};

const answer = multiply(5, 4);

console.log(answer);
```

Output:

```text
20
```
