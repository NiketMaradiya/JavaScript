# Truthy and Falsy Values in JavaScript

## What Are Truthy and Falsy Values?

In JavaScript, every value behaves like either `true` or `false` when used inside a condition.

A value that behaves like `true` is called a **truthy value**.

A value that behaves like `false` is called a **falsy value**.

Example:

```javascript
if ("Hello") {
  console.log("This value is truthy");
}
```

Output:

```text
This value is truthy
```

---

# Falsy Values in JavaScript

The main falsy values are:

```javascript
false
0
-0
0n
""
null
undefined
NaN
```

---

## 1. `false`

The Boolean value `false` is falsy.

```javascript
if (false) {
  console.log("This will run");
} else {
  console.log("False is falsy");
}
```

Output:

```text
False is falsy
```

---

## 2. Number `0`

The number `0` is falsy.

```javascript
let quantity = 0;

if (quantity) {
  console.log("Product available");
} else {
  console.log("Product not available");
}
```

Output:

```text
Product not available
```

---

## 3. Negative Zero `-0`

Negative zero is also falsy.

```javascript
console.log(Boolean(-0));
```

Output:

```text
false
```

---

## 4. BigInt Zero `0n`

BigInt zero is falsy.

```javascript
console.log(Boolean(0n));
```

Output:

```text
false
```

But other BigInt values are truthy.

```javascript
console.log(Boolean(10n));
```

Output:

```text
true
```

---

## 5. Empty String `""`

An empty string is falsy.

```javascript
let name = "";

if (name) {
  console.log("Name available");
} else {
  console.log("Name is empty");
}
```

Output:

```text
Name is empty
```

These are empty strings:

```javascript
""
''
``
```

But a string containing a space is truthy.

```javascript
console.log(Boolean(" "));
```

Output:

```text
true
```

---

## 6. `null`

`null` means an intentionally empty value.

```javascript
let selectedProduct = null;

if (selectedProduct) {
  console.log("Product selected");
} else {
  console.log("No product selected");
}
```

Output:

```text
No product selected
```

---

## 7. `undefined`

When a variable has no assigned value, it is `undefined`.

```javascript
let email;

console.log(email);
```

Output:

```text
undefined
```

`undefined` is falsy.

```javascript
if (email) {
  console.log("Email available");
} else {
  console.log("Email not available");
}
```

Output:

```text
Email not available
```

---

## 8. `NaN`

`NaN` means Not a Number.

```javascript
let result = Number("Hello");

console.log(result);
```

Output:

```text
NaN
```

`NaN` is falsy.

```javascript
console.log(Boolean(NaN));
```

Output:

```text
false
```

---

# All Falsy Values Example

```javascript
console.log(Boolean(false));
console.log(Boolean(0));
console.log(Boolean(-0));
console.log(Boolean(0n));
console.log(Boolean(""));
console.log(Boolean(null));
console.log(Boolean(undefined));
console.log(Boolean(NaN));
```

Output:

```text
false
false
false
false
false
false
false
false
```

---

# Truthy Values in JavaScript

Almost every value except falsy values is truthy.

Common truthy values:

```javascript
true
1
-1
100
"Hello"
"0"
"false"
" "
[]
{}
function () {}
Infinity
-Infinity
10n
```

---

## Non-Zero Numbers Are Truthy

```javascript
console.log(Boolean(1));
console.log(Boolean(-1));
console.log(Boolean(100));
console.log(Boolean(3.14));
```

Output:

```text
true
true
true
true
```

---

## Non-Empty Strings Are Truthy

```javascript
console.log(Boolean("Hello"));
console.log(Boolean("Niket"));
console.log(Boolean("0"));
console.log(Boolean("false"));
console.log(Boolean(" "));
```

Output:

```text
true
true
true
true
true
```

Important:

```javascript
"false"
```

is a string, not the Boolean value `false`.

Therefore:

```javascript
console.log(Boolean("false"));
```

Output:

```text
true
```

---

## Empty Array Is Truthy

An empty array is truthy.

```javascript
console.log(Boolean([]));
```

Output:

```text
true
```

To check whether an array has data:

```javascript
let products = [];

if (products.length > 0) {
  console.log("Products available");
} else {
  console.log("No products available");
}
```

Output:

```text
No products available
```

---

## Empty Object Is Truthy

An empty object is truthy.

```javascript
console.log(Boolean({}));
```

Output:

```text
true
```

To check whether an object contains properties:

```javascript
let user = {};

if (Object.keys(user).length > 0) {
  console.log("Object contains data");
} else {
  console.log("Object is empty");
}
```

Output:

```text
Object is empty
```

---

## Functions Are Truthy

Functions are truthy values.

```javascript
function greet() {
  console.log("Hello");
}

if (greet) {
  console.log("Function exists");
}
```

Output:

```text
Function exists
```

---

## Infinity Is Truthy

```javascript
console.log(Boolean(Infinity));
console.log(Boolean(-Infinity));
```

Output:

```text
true
true
```

---

# Using `Boolean()`

The `Boolean()` function converts a value into `true` or `false`.

```javascript
console.log(Boolean(100));
console.log(Boolean(0));
console.log(Boolean("Hello"));
console.log(Boolean(""));
console.log(Boolean(null));
```

Output:

```text
true
false
true
false
false
```

---

# Using Double NOT `!!`

The double NOT operator converts a value into Boolean.

```javascript
console.log(!!"Hello");
console.log(!!"");
console.log(!!100);
console.log(!!0);
```

Output:

```text
true
false
true
false
```

`Boolean(value)` and `!!value` normally give the same result.

---

# Truthy and Falsy with `if`

```javascript
let password = "";

if (password) {
  console.log("Password entered");
} else {
  console.log("Please enter a password");
}
```

Output:

```text
Please enter a password
```

---

# Logical AND `&&`

The `&&` operator returns the first falsy value.

If all values are truthy, it returns the last value.

```javascript
console.log("Hello" && 100);
```

Output:

```text
100
```

Both values are truthy, so the last value is returned.

```javascript
console.log(0 && "Hello");
```

Output:

```text
0
```

`0` is the first falsy value.

Practical example:

```javascript
let isLoggedIn = true;

isLoggedIn && console.log("Welcome user");
```

Output:

```text
Welcome user
```

---

# Logical OR `||`

The `||` operator returns the first truthy value.

```javascript
console.log("" || "Guest");
```

Output:

```text
Guest
```

```javascript
console.log("Niket" || "Guest");
```

Output:

```text
Niket
```

Default value example:

```javascript
let username = "";
let displayName = username || "Guest";

console.log(displayName);
```

Output:

```text
Guest
```

---

# Problem with `||`

Suppose zero is a valid value.

```javascript
let quantity = 0;

let finalQuantity = quantity || 10;

console.log(finalQuantity);
```

Output:

```text
10
```

This happens because `0` is falsy.

Use `??` instead:

```javascript
let quantity = 0;

let finalQuantity = quantity ?? 10;

console.log(finalQuantity);
```

Output:

```text
0
```

---

# Difference Between `||` and `??`

`||` uses the second value when the first value is falsy.

`??` uses the second value only when the first value is `null` or `undefined`.

```javascript
console.log(0 || 10);
console.log(0 ?? 10);
```

Output:

```text
10
0
```

More examples:

```javascript
console.log("" || "Guest");
console.log("" ?? "Guest");

console.log(false || true);
console.log(false ?? true);
```

Output:

```text
Guest

true
false
```

---

# Logical NOT `!`

The NOT operator reverses the Boolean result.

```javascript
console.log(!"Hello");
console.log(!"");
console.log(!100);
console.log(!0);
```

Output:

```text
false
true
false
true
```

---

# Form Validation Example

```javascript
let username = "Niket";
let password = "123456";

if (username && password) {
  console.log("Form submitted successfully");
} else {
  console.log("Please fill all fields");
}
```

Output:

```text
Form submitted successfully
```

---

# Login Example

```javascript
let email = "admin@gmail.com";
let password = "Admin@123";

if (email && password) {
  console.log("Trying to log in...");
} else {
  console.log("Email and password are required");
}
```

Output:

```text
Trying to log in...
```

---

# Important Differences

## `false` and `"false"`

```javascript
console.log(Boolean(false));
console.log(Boolean("false"));
```

Output:

```text
false
true
```

`false` is a Boolean.

`"false"` is a non-empty string.

---

## `0` and `"0"`

```javascript
console.log(Boolean(0));
console.log(Boolean("0"));
```

Output:

```text
false
true
```

`0` is a number.

`"0"` is a non-empty string.

---

## Empty Array

```javascript
console.log(Boolean([]));
```

Output:

```text
true
```

---

## Empty Object

```javascript
console.log(Boolean({}));
```

Output:

```text
true
```

---

# Truthy and Falsy Table

| Value       | Boolean Result |
| ----------- | -------------- |
| `false`     | `false`        |
| `0`         | `false`        |
| `-0`        | `false`        |
| `0n`        | `false`        |
| `""`        | `false`        |
| `null`      | `false`        |
| `undefined` | `false`        |
| `NaN`       | `false`        |
| `true`      | `true`         |
| `1`         | `true`         |
| `-1`        | `true`         |
| `"Hello"`   | `true`         |
| `"0"`       | `true`         |
| `"false"`   | `true`         |
| `" "`       | `true`         |
| `[]`        | `true`         |
| `{}`        | `true`         |

---

# Interview Questions and Answers

## 1. What are truthy and falsy values?

Truthy values behave like `true` inside a condition.

Falsy values behave like `false` inside a condition.

---

## 2. What are the falsy values in JavaScript?

```javascript
false
0
-0
0n
""
null
undefined
NaN
```

---

## 3. Is an empty array truthy or falsy?

An empty array is truthy.

```javascript
console.log(Boolean([]));
```

Output:

```text
true
```

---

## 4. Is an empty object truthy or falsy?

An empty object is truthy.

```javascript
console.log(Boolean({}));
```

Output:

```text
true
```

---

## 5. Is `"false"` falsy?

No.

`"false"` is a non-empty string, so it is truthy.

```javascript
console.log(Boolean("false"));
```

Output:

```text
true
```

---

## 6. Is `"0"` falsy?

No.

`"0"` is a non-empty string, so it is truthy.

```javascript
console.log(Boolean("0"));
```

Output:

```text
true
```

---

## 7. What does `!!` do?

It converts a value into Boolean.

```javascript
console.log(!!"Hello");
console.log(!!0);
```

Output:

```text
true
false
```

---

## 8. What is the output?

```javascript
console.log(Boolean(" "));
```

Answer:

```text
true
```

Because the string contains a space.

---

## 9. What is the output?

```javascript
if ([]) {
  console.log("Hello");
}
```

Answer:

```text
Hello
```

Because an empty array is truthy.

---

## 10. What is the output?

```javascript
if ({}) {
  console.log("Object");
}
```

Answer:

```text
Object
```

Because an empty object is truthy.

---

## 11. What is the output?

```javascript
console.log("" || "Guest");
```

Answer:

```text
Guest
```

---

## 12. What is the output?

```javascript
console.log("Niket" && 100);
```

Answer:

```text
100
```

---

## 13. What is the output?

```javascript
console.log(0 && "Hello");
```

Answer:

```text
0
```

---

## 14. What is the output?

```javascript
console.log(false || 0 || null || "JavaScript");
```

Answer:

```text
JavaScript
```

---

## 15. What is short-circuit evaluation?

JavaScript stops checking values when it already knows the result.

With `&&`, JavaScript stops at the first falsy value.

With `||`, JavaScript stops at the first truthy value.

```javascript
false && console.log("Will not run");

true || console.log("Will not run");
```

---

## 16. What is the difference between `||` and `??`?

`||` uses the second value when the first value is any falsy value.

`??` uses the second value only when the first value is `null` or `undefined`.

```javascript
console.log(0 || 10);
console.log(0 ?? 10);
```

Output:

```text
10
0
```

---

## 17. Why is this code incorrect?

```javascript
let products = [];

if (products) {
  console.log("Products available");
}
```

Because an empty array is truthy.

Correct code:

```javascript
if (products.length > 0) {
  console.log("Products available");
}
```

---

## 18. What is the output?

```javascript
console.log(!"Hello");
console.log(!!"Hello");
```

Answer:

```text
false
true
```

---

## 19. What is the output?

```javascript
let value = NaN;

if (value) {
  console.log("A");
} else {
  console.log("B");
}
```

Answer:

```text
B
```

Because `NaN` is falsy.

---

## 20. What is the output?

```javascript
console.log([] || "Default");
console.log({} || "Default");
```

Answer:

```text
[]
{}
```

Because arrays and objects are truthy.

---

# Practice Questions

## Question 1

```javascript
console.log(Boolean(""));
console.log(Boolean(" "));
console.log(Boolean(0));
console.log(Boolean("0"));
console.log(Boolean([]));
console.log(Boolean({}));
console.log(Boolean(null));
console.log(Boolean(undefined));
```

Answer:

```text
false
true
false
true
true
true
false
false
```

---

## Question 2

```javascript
let username = "";

console.log(username || "Guest");
```

Answer:

```text
Guest
```

---

## Question 3

```javascript
let age = 0;

console.log(age ?? 18);
```

Answer:

```text
0
```

---

## Question 4

```javascript
console.log(false || "" || null || 100);
```

Answer:

```text
100
```

---

## Question 5

```javascript
console.log("Hello" && 0 && "JavaScript");
```

Answer:

```text
0
```

Because `0` is the first falsy value.

---

# Final Summary

Falsy values:

```javascript
false
0
-0
0n
""
null
undefined
NaN
```

Everything else is generally truthy.

Important examples:

```javascript
Boolean([]);       // true
Boolean({});       // true
Boolean("false");  // true
Boolean("0");      // true
Boolean(" ");      // true
Boolean(0);        // false
Boolean("");       // false
Boolean(null);     // false
```

Use:

```javascript
Boolean(value)
```

or:

```javascript
!!value
```

to convert a value into Boolean.
