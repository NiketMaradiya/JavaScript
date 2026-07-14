# Arrow Functions (=>) in JavaScript

## What is an Arrow Function?

An Arrow Function is a shorter way to write a function in JavaScript.

It was introduced in **ES6 (ECMAScript 2015)**.

Instead of using the `function` keyword, we use the **arrow (`=>`)** operator.

### Normal Function

```javascript
function greet() {
    console.log("Hello");
}
```

### Arrow Function

```javascript
const greet = () => {
    console.log("Hello");
};
```

Output

```
Hello
```

---

# Why Use Arrow Functions?

Arrow Functions make your code:

- Shorter
- Cleaner
- Easier to read
- Perfect for callbacks
- Commonly used in React, Node.js, and Modern JavaScript

---

# Syntax

## 1. No Parameters

```javascript
const greet = () => {
    console.log("Hello");
};

greet();
```

Output

```
Hello
```

---

## 2. One Parameter

```javascript
const square = num => {
    return num * num;
};

console.log(square(5));
```

Output

```
25
```

You can also write:

```javascript
const square = (num) => {
    return num * num;
};
```

Both are correct.

---

## 3. Multiple Parameters

```javascript
const add = (a, b) => {
    return a + b;
};

console.log(add(10, 20));
```

Output

```
30
```

When there are two or more parameters, parentheses `()` are required.

---

# Implicit Return

If there is only one statement, you don't need `return`.

Normal

```javascript
const multiply = (a, b) => {
    return a * b;
};
```

Short Form

```javascript
const multiply = (a, b) => a * b;

console.log(multiply(5, 4));
```

Output

```
20
```

---

# Returning an Object

Wrong

```javascript
const person = () => {
    name: "Niket";
};

console.log(person());
```

Output

```
undefined
```

Correct

```javascript
const person = () => ({
    name: "Niket"
});

console.log(person());
```

Output

```
{ name: 'Niket' }
```

---

# Arrow Function with Default Parameters

```javascript
const greet = (name = "Guest") => {
    console.log("Hello " + name);
};

greet();
greet("Niket");
```

Output

```
Hello Guest
Hello Niket
```

---

# Arrow Function with Array Methods

## map()

```javascript
const numbers = [1, 2, 3];

const result = numbers.map(num => num * 2);

console.log(result);
```

Output

```
[2, 4, 6]
```

---

## filter()

```javascript
const numbers = [10, 15, 20, 25];

const even = numbers.filter(num => num % 2 === 0);

console.log(even);
```

Output

```
[10, 20]
```

---

## reduce()

```javascript
const numbers = [1, 2, 3, 4];

const total = numbers.reduce((sum, num) => sum + num, 0);

console.log(total);
```

Output

```
10
```

---

# Arrow Function as Callback

```javascript
setTimeout(() => {
    console.log("Executed after 2 seconds");
}, 2000);
```

Output

```
Executed after 2 seconds
```

---

# Arrow Function and "this"

Normal Function

```javascript
const user = {
    name: "Niket",

    greet: function () {
        console.log(this.name);
    }
};

user.greet();
```

Output

```
Niket
```

Arrow Function

```javascript
const user = {
    name: "Niket",

    greet: () => {
        console.log(this.name);
    }
};

user.greet();
```

Output

```
undefined
```

### Why?

Arrow Functions **do not have their own `this`**.

They use `this` from the surrounding scope.

---

# Arrow Function and arguments

Normal Function

```javascript
function test() {
    console.log(arguments);
}

test(1, 2, 3);
```

Output

```
[1, 2, 3]
```

Arrow Function

```javascript
const test = () => {
    console.log(arguments);
};

test(1, 2, 3);
```

Output

```
ReferenceError: arguments is not defined
```

Correct Way

```javascript
const test = (...args) => {
    console.log(args);
};

test(1, 2, 3);
```

Output

```
[1, 2, 3]
```

---

# Arrow Function Cannot Be Constructor

Wrong

```javascript
const Person = (name) => {
    this.name = name;
};

const p = new Person("Niket");
```

Output

```
TypeError: Person is not a constructor
```

Correct

```javascript
function Person(name) {
    this.name = name;
}

const p = new Person("Niket");

console.log(p.name);
```

Output

```
Niket
```

---

# Difference Between Normal Function and Arrow Function

| Normal Function | Arrow Function |
|-----------------|----------------|
| Uses `function` keyword | Uses `=>` |
| Has its own `this` | Uses lexical `this` |
| Has `arguments` | No `arguments` |
| Can be used with `new` | Cannot be used with `new` |
| Best for object methods | Best for callbacks |

---

# Common Errors

## Error 1: Missing Parentheses for Multiple Parameters

Wrong

```javascript
const add = a, b => a + b;
```

Error

```
SyntaxError: Unexpected token ','
```

Correct

```javascript
const add = (a, b) => a + b;
```

---

## Error 2: Forgetting return

Wrong

```javascript
const square = (num) => {
    num * num;
};

console.log(square(5));
```

Output

```
undefined
```

Correct

```javascript
const square = (num) => {
    return num * num;
};
```

Or

```javascript
const square = num => num * num;
```

Output

```
25
```

---

## Error 3: Returning Object Incorrectly

Wrong

```javascript
const user = () => {
    name: "Niket";
};
```

Output

```
undefined
```

Correct

```javascript
const user = () => ({
    name: "Niket"
});
```

---

## Error 4: Using Arrow Function as Object Method

Wrong

```javascript
const car = {
    brand: "BMW",

    show: () => {
        console.log(this.brand);
    }
};

car.show();
```

Output

```
undefined
```

Correct

```javascript
const car = {
    brand: "BMW",

    show() {
        console.log(this.brand);
    }
};

car.show();
```

Output

```
BMW
```

---

## Error 5: Using new with Arrow Function

Wrong

```javascript
const Animal = () => {};

const dog = new Animal();
```

Output

```
TypeError: Animal is not a constructor
```

---

# Advantages

- Less code
- Easy to read
- Automatic return for one expression
- Great for callbacks
- Widely used in React
- Perfect for array methods

---

# Disadvantages

- No own `this`
- No `arguments` object
- Cannot be used as constructor
- Not suitable for object methods

---

# Real-World Examples

## Example 1: Calculate Discount

```javascript
const discount = (price, percent) => price - (price * percent / 100);

console.log(discount(1000, 20));
```

Output

```
800
```

---

## Example 2: Check Even Number

```javascript
const isEven = num => num % 2 === 0;

console.log(isEven(10));
console.log(isEven(7));
```

Output

```
true
false
```

---

## Example 3: Convert Name to Uppercase

```javascript
const upper = name => name.toUpperCase();

console.log(upper("niket"));
```

Output

```
NIKET
```

---

## Example 4: Find Maximum Number

```javascript
const max = (a, b) => a > b ? a : b;

console.log(max(15, 25));
```

Output

```
25
```

---

# Interview Questions

## 1. What is an Arrow Function?

An Arrow Function is a shorter syntax for writing functions introduced in ES6 using the `=>` operator.

---

## 2. When were Arrow Functions introduced?

ES6 (ECMAScript 2015).

---

## 3. Does an Arrow Function have its own `this`?

No.

---

## 4. Can Arrow Functions be used as constructors?

No.

---

## 5. Do Arrow Functions have the `arguments` object?

No.

Use Rest Parameters (`...args`) instead.

---

## 6. What is an Implicit Return?

When an Arrow Function has only one expression, JavaScript automatically returns the result.

Example

```javascript
const add = (a, b) => a + b;
```

---

## 7. Where are Arrow Functions mostly used?

- React
- Node.js
- Array methods (`map`, `filter`, `reduce`)
- Promise callbacks
- Event callbacks
- Async functions

---

# Summary

- Introduced in ES6.
- Uses the `=>` operator.
- Shorter than normal functions.
- Supports implicit return.
- Does not have its own `this`.
- Does not have the `arguments` object.
- Cannot be used with `new`.
- Best for callbacks, array methods, and small utility functions.
- Avoid using them as object methods or constructors.