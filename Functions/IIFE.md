# IIFE (Immediately Invoked Function Expression) in JavaScript

## What is an IIFE?

**IIFE** stands for **Immediately Invoked Function Expression**.

An IIFE is a function that is created and executed immediately after it is defined.

Unlike a normal function, you don't need to call it separately.

---

# Why is it called "Immediately Invoked Function Expression"?

- **Immediately** → Runs as soon as JavaScript reads it.
- **Invoked** → The function is called automatically.
- **Function Expression** → The function is written as an expression, not a declaration.

---

# Syntax

```javascript
(function () {
    // Code
})();
```

OR

```javascript
(() => {
    // Code
})();
```

---

# Normal Function vs IIFE

## Normal Function

```javascript
function greet() {
    console.log("Hello");
}

greet();
```

### Output

```
Hello
```

The function is created first and then called manually.

---

## IIFE

```javascript
(function () {
    console.log("Hello");
})();
```

### Output

```
Hello
```

The function is created and called immediately.

---

# How IIFE Works

```javascript
(function () {
    console.log("Welcome");
})();
```

### Step 1

JavaScript creates a function.

```
Function Created
```

↓

### Step 2

The `()` at the end immediately calls the function.

```
Function Called
```

↓

### Step 3

The code inside the function runs.

```
Welcome
```

↓

### Step 4

The function finishes and its local memory is removed.

---

# Why Do We Use IIFE?

IIFE is mainly used for:

- Running code only once.
- Avoiding global variables.
- Creating private variables.
- Keeping code organized.
- Preventing variable name conflicts.

---

# Example 1: Simple IIFE

```javascript
(function () {
    console.log("Welcome to JavaScript");
})();
```

### Output

```
Welcome to JavaScript
```

---

# Example 2: IIFE with Parameters

```javascript
(function (name) {
    console.log("Hello " + name);
})("Niket");
```

### Output

```
Hello Niket
```

Explanation

```
name = "Niket"

↓

Hello Niket
```

---

# Example 3: IIFE Returning a Value

```javascript
const result = (function () {
    return 50 + 20;
})();

console.log(result);
```

### Output

```
70
```

Memory

```
result → 70
```

---

# Example 4: Private Variables

```javascript
(function () {
    let password = "abc123";

    console.log(password);
})();
```

### Output

```
abc123
```

Outside the IIFE

```javascript
console.log(password);
```

### Output

```
ReferenceError: password is not defined
```

Explanation

The variable exists only inside the IIFE.

---

# Example 5: Arrow Function IIFE

```javascript
(() => {
    console.log("Arrow Function IIFE");
})();
```

### Output

```
Arrow Function IIFE
```

---

# Example 6: Arrow IIFE with Parameters

```javascript
((a, b) => {
    console.log(a + b);
})(20, 30);
```

### Output

```
50
```

---

# Example 7: Named IIFE

```javascript
(function display() {
    console.log("JavaScript");
})();
```

### Output

```
JavaScript
```

Trying to call it outside

```javascript
display();
```

### Output

```
ReferenceError: display is not defined
```

---

# Example 8: Configuration Object

```javascript
const config = (function () {
    return {
        appName: "My App",
        version: "1.0.0"
    };
})();

console.log(config);
```

### Output

```javascript
{
  appName: "My App",
  version: "1.0.0"
}
```

---

# Example 9: Avoid Global Variables

Without IIFE

```javascript
var count = 1;

console.log(count);
```

### Output

```
1
```

`count` becomes a global variable.

Using IIFE

```javascript
(function () {
    let count = 1;

    console.log(count);
})();
```

### Output

```
1
```

Outside

```javascript
console.log(count);
```

### Output

```
ReferenceError: count is not defined
```

---

# Real World Example

Imagine two JavaScript files.

## file1.js

```javascript
var total = 100;
```

## file2.js

```javascript
var total = 200;
```

Both variables are global.

This causes conflicts.

Using IIFE

```javascript
(function () {
    var total = 100;
})();
```

```javascript
(function () {
    var total = 200;
})();
```

Now each `total` variable is private.

No conflicts occur.

---

# Memory Diagram

Before Execution

```
Global Scope
```

↓

During IIFE

```
Global Scope

↓

IIFE Scope

name → Niket

age → 22
```

↓

After Execution

```
Global Scope

(IIFE variables removed)
```

---

# Common Errors

## Error 1: Missing Parentheses

❌ Wrong

```javascript
function () {
    console.log("Hello");
}();
```

### Error

```
SyntaxError: Function statements require a function name
```

✅ Correct

```javascript
(function () {
    console.log("Hello");
})();
```

---

## Error 2: Forgetting to Call the Function

❌ Wrong

```javascript
(function () {
    console.log("Hello");
});
```

### Result

```
Nothing happens
```

The function is created but never executed.

✅ Correct

```javascript
(function () {
    console.log("Hello");
})();
```

---

## Error 3: Accessing Private Variables

❌ Wrong

```javascript
(function () {
    let city = "Ahmedabad";
})();

console.log(city);
```

### Error

```
ReferenceError: city is not defined
```

Reason

The variable exists only inside the IIFE.

---

## Error 4: Missing Closing Parenthesis

❌ Wrong

```javascript
(function () {
    console.log("Hello");
();
```

### Error

```
SyntaxError: Unexpected token
```

---

## Error 5: Missing Semicolon Before an IIFE

❌ Wrong

```javascript
const number = 10
(function () {
    console.log("Hello");
})();
```

### Possible Error

```
TypeError: 10 is not a function
```

✅ Correct

```javascript
const number = 10;

(function () {
    console.log("Hello");
})();
```

OR

```javascript
const number = 10

;(function () {
    console.log("Hello");
})();
```

---

# Advantages

- Runs immediately.
- Creates private scope.
- Prevents global variable pollution.
- Avoids variable name conflicts.
- Good for one-time initialization.
- Keeps code clean and organized.

---

# Disadvantages

- Cannot be reused after execution.
- Can make debugging harder if overused.
- Less common in modern JavaScript because `let`, `const`, and ES Modules provide better scope management.

---

# IIFE vs Normal Function

| Feature | Normal Function | IIFE |
|----------|-----------------|------|
| Called manually | ✅ Yes | ❌ No |
| Executes immediately | ❌ No | ✅ Yes |
| Reusable | ✅ Yes | ❌ No |
| Accepts parameters | ✅ Yes | ✅ Yes |
| Returns values | ✅ Yes | ✅ Yes |
| Creates local scope | ✅ Yes | ✅ Yes |
| Best for one-time execution | ❌ No | ✅ Yes |

---

# Interview Questions

## 1. What is IIFE?

**Answer:** IIFE stands for **Immediately Invoked Function Expression**. It is a function that executes immediately after it is defined.

---

## 2. Why do we use IIFE?

**Answer:**

- To execute code immediately.
- To create private variables.
- To avoid global scope pollution.

---

## 3. Why are parentheses required in IIFE?

**Answer:**

They convert a function declaration into a function expression, allowing it to be executed immediately.

---

## 4. Can an IIFE accept parameters?

**Answer:** Yes.

```javascript
(function (name) {
    console.log(name);
})("Niket");
```

---

## 5. Can an IIFE return a value?

**Answer:** Yes.

```javascript
const total = (function () {
    return 100 + 200;
})();

console.log(total);
```

Output

```
300
```

---

## 6. Is IIFE still used in modern JavaScript?

**Answer:**

Yes, but less frequently. Modern JavaScript uses **let**, **const**, and **ES Modules** to provide scope. However, IIFEs are still useful for one-time initialization and encapsulating code.

---

# Summary

- IIFE = Immediately Invoked Function Expression.
- Executes as soon as it is created.
- Helps avoid global variables.
- Creates a private scope.
- Useful for initialization code.
- Supports parameters and return values.
- Still useful, though less common with modern JavaScript features.