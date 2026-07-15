# Callback Functions in JavaScript

A **Callback Function** is a function that is passed as an argument to another function. The receiving function executes the callback at the appropriate time.

---

# Syntax

```javascript
function mainFunction(callback) {
  // Some work
  callback();
}

function callbackFunction() {
  console.log("Callback executed");
}

mainFunction(callbackFunction);
```

---

# Why Do We Use Callback Functions?

- To execute code after another function finishes.
- To make functions reusable.
- To handle asynchronous operations.
- Used in array methods like `map()`, `filter()`, `forEach()`.
- Commonly used in Node.js and JavaScript APIs.

---

# Basic Example

```javascript
function greet(name, callback) {
  console.log("Hello " + name);

  callback();
}

function welcome() {
  console.log("Welcome to JavaScript");
}

greet("Niket", welcome);
```

### Output

```
Hello Niket
Welcome to JavaScript
```

---

# How It Works

```
greet("Niket", welcome)

↓

name = "Niket"
callback = welcome

↓

console.log("Hello Niket")

↓

callback()

↓

welcome()

↓

console.log("Welcome to JavaScript")
```

---

# Callback with Parameters

```javascript
function calculate(a, b, callback) {
  let result = a + b;

  callback(result);
}

function display(answer) {
  console.log("Answer:", answer);
}

calculate(10, 20, display);
```

### Output

```
Answer: 30
```

---

# Anonymous Callback

```javascript
function greet(name, callback) {
  console.log("Hello " + name);

  callback();
}

greet("Niket", function () {
  console.log("Have a nice day!");
});
```

### Output

```
Hello Niket
Have a nice day!
```

---

# Arrow Function Callback

```javascript
function greet(name, callback) {
  console.log("Hello " + name);

  callback();
}

greet("Niket", () => {
  console.log("Welcome!");
});
```

### Output

```
Hello Niket
Welcome!
```

---

# Callback with forEach()

```javascript
const fruits = ["Apple", "Banana", "Mango"];

fruits.forEach(function (fruit) {
  console.log(fruit);
});
```

### Output

```
Apple
Banana
Mango
```

---

# Callback with map()

```javascript
const numbers = [1, 2, 3, 4];

const double = numbers.map(function (num) {
  return num * 2;
});

console.log(double);
```

### Output

```
[2, 4, 6, 8]
```

---

# Callback with filter()

```javascript
const numbers = [10, 15, 20, 25, 30];

const result = numbers.filter(function (num) {
  return num > 20;
});

console.log(result);
```

### Output

```
[25, 30]
```

---

# Synchronous Callback

```javascript
function process(callback) {
  console.log("Start");

  callback();

  console.log("End");
}

process(() => {
  console.log("Running callback");
});
```

### Output

```
Start
Running callback
End
```

---

# Asynchronous Callback

```javascript
console.log("Start");

setTimeout(() => {
  console.log("Callback executed");
}, 2000);

console.log("End");
```

### Output

```
Start
End
Callback executed
```

---

# Real-Life Example

```javascript
function prepareFood(food, callback) {
  console.log("Preparing " + food);

  setTimeout(() => {
    console.log(food + " is ready");

    callback();
  }, 2000);
}

prepareFood("Pizza", () => {
  console.log("Please collect your order.");
});
```

### Output

```
Preparing Pizza
Pizza is ready
Please collect your order.
```

---

# Success and Error Callback

```javascript
function divide(a, b, success, error) {
  if (b === 0) {
    error("Cannot divide by zero");
    return;
  }

  success(a / b);
}

divide(
  20,
  4,
  (result) => console.log(result),
  (err) => console.log(err)
);

divide(
  20,
  0,
  (result) => console.log(result),
  (err) => console.log(err)
);
```

### Output

```
5
Cannot divide by zero
```

---

# Node.js Error-First Callback

```javascript
function getUser(id, callback) {
  if (!id) {
    callback("User ID missing", null);
    return;
  }

  callback(null, {
    id: id,
    name: "Niket",
  });
}

getUser(1, (error, user) => {
  if (error) {
    console.log(error);
    return;
  }

  console.log(user);
});
```

### Output

```
{ id: 1, name: 'Niket' }
```

---

# Common Errors

## Error 1: Callback is Not a Function

### Wrong

```javascript
function greet(name, callback) {
  callback();
}

greet("Niket", "Hello");
```

### Error

```
TypeError: callback is not a function
```

### Correct

```javascript
greet("Niket", () => {
  console.log("Hello");
});
```

---

## Error 2: Calling Function While Passing

### Wrong

```javascript
function welcome() {
  console.log("Welcome");
}

greet("Niket", welcome());
```

### Error

```
TypeError: callback is not a function
```

### Correct

```javascript
greet("Niket", welcome);
```

---

## Error 3: Forgetting to Call Callback

### Wrong

```javascript
function add(a, b, callback) {
  let result = a + b;
}

add(10, 20, (result) => {
  console.log(result);
});
```

### Output

```
Nothing
```

### Correct

```javascript
function add(a, b, callback) {
  let result = a + b;

  callback(result);
}
```

---

## Error 4: Calling Callback Multiple Times

### Wrong

```javascript
function check(number, callback) {
  if (number > 0) {
    callback("Positive");
  }

  callback("Done");
}

check(10, console.log);
```

### Output

```
Positive
Done
```

### Correct

```javascript
function check(number, callback) {
  if (number > 0) {
    callback("Positive");
    return;
  }

  callback("Negative");
}
```

---

## Error 5: Not Handling Error

### Wrong

```javascript
function divide(a, b, callback) {
  if (b === 0) {
    callback(new Error("Divide by zero"));
    return;
  }

  callback(null, a / b);
}

divide(10, 0, (error, result) => {
  console.log(result);
});
```

### Correct

```javascript
divide(10, 0, (error, result) => {
  if (error) {
    console.log(error.message);
    return;
  }

  console.log(result);
});
```

---

## Error 6: Callback Hell

```javascript
login(function () {
  profile(function () {
    orders(function () {
      payment(function () {
        console.log("Completed");
      });
    });
  });
});
```

This is called **Callback Hell** or **Pyramid of Doom**.

Today we generally use:

- Promise
- Async/Await

---

# Validate Callback

```javascript
function greet(name, callback) {
  console.log("Hello " + name);

  if (typeof callback === "function") {
    callback();
  }
}

greet("Niket");
```

---

# Return Value from Callback

```javascript
function calculate(a, b, callback) {
  return callback(a, b);
}

const result = calculate(10, 20, (x, y) => {
  return x + y;
});

console.log(result);
```

### Output

```
30
```

---

# Complete Example

```javascript
function createUser(name, callback) {
  setTimeout(() => {
    callback({
      id: 1,
      name: name,
    });
  }, 1000);
}

createUser("Niket", (user) => {
  console.log(user);
});
```

### Output

```
{
  id: 1,
  name: "Niket"
}
```

---

# Advantages

- Easy to reuse functions.
- Executes code after another task.
- Useful for asynchronous programming.
- Used in APIs and event handling.
- Used in array methods.

---

# Disadvantages

- Callback Hell.
- Difficult debugging.
- Difficult error handling.
- Nested code becomes hard to read.
- Modern JavaScript prefers Promises and Async/Await.

---

# Callback vs Normal Function

## Normal Function

```javascript
function hello() {
  console.log("Hello");
}

hello();
```

## Callback Function

```javascript
function execute(callback) {
  callback();
}

function hello() {
  console.log("Hello");
}

execute(hello);
```

---

# Interview Questions

### 1. What is a Callback Function?

A function passed as an argument to another function and executed later.

---

### 2. Why are Callback Functions used?

To execute code after another task completes and to handle asynchronous operations.

---

### 3. What is Callback Hell?

Deeply nested callback functions that make code difficult to read and maintain.

---

### 4. How can Callback Hell be avoided?

- Promises
- Async/Await

---

### 5. Difference between `callback` and `callback()`?

| callback | callback() |
|----------|------------|
| Passes the function | Executes the function |

---

### 6. What is an Error-First Callback?

A callback where the first parameter is an error and the second is the result.

Example:

```javascript
callback(error, result);
```

---

# Quick Summary

- Callback = Function passed into another function.
- Executed later by the receiving function.
- Used in synchronous and asynchronous programming.
- Common in `setTimeout()`, `forEach()`, `map()`, `filter()`, Node.js APIs.
- Prevent Callback Hell using Promises or Async/Await.