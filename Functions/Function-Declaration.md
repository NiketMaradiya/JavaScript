# Function Declaration in JavaScript

A **Function Declaration** is the most common way to create a function in JavaScript. It allows you to write a block of code once and use it many times by calling the function.

---

# Table of Contents

1. What is a Function?
2. Why Do We Use Functions?
3. Function Declaration Syntax
4. Parts of a Function
5. Simple Example
6. Function with Parameters
7. Function with Return Value
8. Function Without Return
9. Calling a Function Multiple Times
10. Real-Life Examples
11. Function Hoisting
12. Function Scope
13. Advantages
14. Common Mistakes
15. Function Declaration vs Function Expression
16. Interview Questions
17. Summary

---

# 1. What is a Function?

A **function** is a reusable block of code that performs a specific task.

Instead of writing the same code again and again, you can write it once inside a function and call it whenever needed.

Think of a function like a **coffee machine**.

```
Coffee Beans + Water
        ↓
  Coffee Machine
        ↓
      Coffee
```

A function works the same way.

```
Input
  ↓
Function
  ↓
Output
```

---

# 2. Why Do We Use Functions?

Without functions:

```javascript
console.log("Welcome Niket");
console.log("Welcome Rahul");
console.log("Welcome Amit");
```

With a function:

```javascript
function welcome(name) {
    console.log("Welcome " + name);
}

welcome("Niket");
welcome("Rahul");
welcome("Amit");
```

Benefits:

- Write code once
- Reuse many times
- Easy to understand
- Easy to maintain
- Less duplicate code

---

# 3. Function Declaration Syntax

```javascript
function functionName(parameters) {

    // code

    return value;

}
```

Example

```javascript
function greet() {
    console.log("Hello World");
}
```

---

# 4. Parts of a Function

```javascript
function greet(name) {

    console.log("Hello " + name);

}
```

Explanation

| Part | Description |
|------|-------------|
| function | Keyword used to create a function |
| greet | Function name |
| name | Parameter |
| { } | Function body |
| console.log() | Code inside function |

---

# 5. Simple Example

```javascript
function greet() {
    console.log("Hello World");
}

greet();
```

Output

```
Hello World
```

Execution Flow

```
Program Start
      ↓
Create Function
      ↓
Call greet()
      ↓
Hello World
```

---

# 6. Function with Parameters

Parameters allow us to pass values into a function.

```javascript
function greet(name) {
    console.log("Hello " + name);
}

greet("Niket");
```

Output

```
Hello Niket
```

Another Example

```javascript
function welcome(city) {
    console.log("Welcome to " + city);
}

welcome("Ahmedabad");
```

Output

```
Welcome to Ahmedabad
```

---

# 7. Function with Multiple Parameters

```javascript
function add(a, b) {
    console.log(a + b);
}

add(10, 20);
```

Output

```
30
```

Another Example

```javascript
function multiply(a, b) {
    console.log(a * b);
}

multiply(5, 4);
```

Output

```
20
```

---

# 8. Function with Return Value

A function can send a value back using **return**.

```javascript
function add(a, b) {
    return a + b;
}

let result = add(15, 10);

console.log(result);
```

Output

```
25
```

Memory

```
15 + 10

↓

25

↓

result

↓

console.log()

↓

25
```

---

# 9. Function Without Return

```javascript
function greet() {
    console.log("Hello");
}

let value = greet();

console.log(value);
```

Output

```
Hello
undefined
```

Reason

The function prints the message but doesn't return anything.

---

# 10. Calling a Function Multiple Times

```javascript
function hello(name) {
    console.log("Hello " + name);
}

hello("Niket");
hello("Rahul");
hello("Amit");
```

Output

```
Hello Niket
Hello Rahul
Hello Amit
```

---

# 11. Real-Life Example 1 (Calculate GST)

```javascript
function calculateGST(price) {

    return price + (price * 18 / 100);

}

console.log(calculateGST(1000));
```

Output

```
1180
```

---

# 12. Real-Life Example 2 (Area of Rectangle)

```javascript
function area(length, width) {

    return length * width;

}

console.log(area(20, 10));
```

Output

```
200
```

---

# 13. Real-Life Example 3 (Even or Odd)

```javascript
function checkEvenOdd(number) {

    if (number % 2 === 0) {
        return "Even";
    }

    return "Odd";

}

console.log(checkEvenOdd(10));
console.log(checkEvenOdd(7));
```

Output

```
Even
Odd
```

---

# 14. Real-Life Example 4 (Maximum Number)

```javascript
function maximum(a, b) {

    if (a > b) {
        return a;
    }

    return b;

}

console.log(maximum(80, 45));
```

Output

```
80
```

---

# 15. Function Hoisting

Function Declaration supports hoisting.

You can call the function before writing it.

```javascript
greet();

function greet() {
    console.log("Hello");
}
```

Output

```
Hello
```

JavaScript internally behaves like this:

```javascript
function greet() {
    console.log("Hello");
}

greet();
```

---

# 16. Function Scope

Variables declared inside a function can only be used inside that function.

```javascript
function test() {

    let age = 20;

    console.log(age);

}

test();
```

Output

```
20
```

Outside

```javascript
console.log(age);
```

Output

```
ReferenceError
```

---

# 17. Advantages of Function Declaration

- Reusable code
- Cleaner code
- Easy maintenance
- Better readability
- Less duplicate code
- Easy debugging
- Supports hoisting
- Easy testing

---

# 18. Common Mistakes

## Mistake 1

Forgetting ()

Wrong

```javascript
greet;
```

Correct

```javascript
greet();
```

---

## Mistake 2

Missing return

Wrong

```javascript
function add(a, b) {

    a + b;

}

console.log(add(5, 5));
```

Output

```
undefined
```

Correct

```javascript
function add(a, b) {

    return a + b;

}
```

---

## Mistake 3

Wrong number of arguments

```javascript
function add(a, b) {

    return a + b;

}

console.log(add(10));
```

Output

```
NaN
```

Because

```
a = 10

b = undefined
```

---

# 19. Function Declaration vs Function Expression

| Function Declaration | Function Expression |
|----------------------|--------------------|
| Uses function keyword | Stored inside a variable |
| Hoisted | Not hoisted |
| Can call before declaration | Cannot call before declaration |
| Most common | Used in modern JavaScript |

Example

Function Declaration

```javascript
function greet() {
    console.log("Hello");
}
```

Function Expression

```javascript
const greet = function () {
    console.log("Hello");
};
```

---

# 20. Interview Questions

### 1. What is Function Declaration?

A Function Declaration is the standard way to create a function using the `function` keyword.

---

### 2. Why do we use functions?

To reuse code, reduce duplication, and make programs easier to manage.

---

### 3. What is the difference between parameters and arguments?

Parameters are variables inside the function definition.

Arguments are actual values passed while calling the function.

Example

```javascript
function greet(name) {

    console.log(name);

}

greet("Niket");
```

Parameter → `name`

Argument → `"Niket"`

---

### 4. What is the return keyword?

The `return` keyword sends a value back from the function.

---

### 5. What happens if we don't write return?

The function returns `undefined`.

---

### 6. Can a Function Declaration be called before it is declared?

Yes.

Because Function Declarations are hoisted.

---

### 7. What is hoisting?

Hoisting is JavaScript's behavior of moving Function Declarations to the top of their scope before execution.

---

### 8. What is function scope?

Variables declared inside a function are accessible only inside that function.

---

### 9. Can we call one function from another function?

Yes.

Example

```javascript
function hello() {
    console.log("Hello");
}

function welcome() {

    hello();

    console.log("Welcome");

}

welcome();
```

Output

```
Hello
Welcome
```

---

### 10. Is Function Declaration reusable?

Yes.

A function can be called as many times as needed.

---

# Summary

- Function Declaration is created using the `function` keyword.
- It creates reusable blocks of code.
- Functions can accept parameters.
- Functions can return values using `return`.
- Function Declarations support hoisting.
- Variables inside a function have local scope.
- They improve code readability, reusability, and maintainability.
- Function Declarations are one of the most important concepts in JavaScript and are used in almost every application.