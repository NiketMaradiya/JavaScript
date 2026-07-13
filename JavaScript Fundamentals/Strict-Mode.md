# JavaScript Strict Mode (`"use strict"`)

## What is Strict Mode?

**Strict Mode** is a special mode in JavaScript that helps developers write **cleaner, safer, and error-free code**.

It was introduced in **ECMAScript 5 (ES5)**.

Normally, JavaScript is very flexible and allows many mistakes without showing an error. These mistakes can create bugs that are difficult to find.

Strict Mode makes JavaScript **more strict** by converting many silent mistakes into real errors.

---

# Why Do We Need Strict Mode?

Imagine you accidentally forget to declare a variable.

Without Strict Mode:

```javascript
name = "Niket";

console.log(name);
```

### Output

```
Niket
```

JavaScript automatically creates a global variable.

This is not a good practice because it can cause unexpected bugs.

With Strict Mode:

```javascript
"use strict";

name = "Niket";
```

### Output

```
ReferenceError: name is not defined
```

Strict Mode immediately tells you that something is wrong.

---

# Syntax

Enable Strict Mode by writing:

```javascript
"use strict";
```

Example:

```javascript
"use strict";

let name = "Niket";

console.log(name);
```

### Output

```
Niket
```

---

# Where Can We Use Strict Mode?

## 1. Entire JavaScript File

```javascript
"use strict";

let age = 20;

console.log(age);
```

Everything inside the file follows Strict Mode.

---

## 2. Inside a Function

```javascript
function demo() {
    "use strict";

    let age = 20;

    console.log(age);
}

demo();
```

Only this function follows Strict Mode.

---

# Rules of Strict Mode

---

# Rule 1: Variables Must Be Declared

### Without Strict Mode

```javascript
age = 20;

console.log(age);
```

Output

```
20
```

JavaScript automatically creates a global variable.

---

### With Strict Mode

```javascript
"use strict";

age = 20;
```

Output

```
ReferenceError
```

Correct way:

```javascript
"use strict";

let age = 20;

console.log(age);
```

Output

```
20
```

---

# Rule 2: Duplicate Function Parameters Are Not Allowed

Wrong:

```javascript
"use strict";

function add(a, a) {
    return a + a;
}
```

Output

```
SyntaxError
```

Correct:

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(10, 20));
```

Output

```
30
```

---

# Rule 3: Cannot Delete Variables

Wrong:

```javascript
"use strict";

let age = 20;

delete age;
```

Output

```
SyntaxError
```

Variables cannot be deleted.

---

# Rule 4: Reserved Keywords Cannot Be Used

Wrong:

```javascript
"use strict";

let public = 10;
```

Output

```
SyntaxError
```

Correct:

```javascript
let marks = 10;
```

---

# Rule 5: `this` Changes

Without Strict Mode

```javascript
function show() {
    console.log(this);
}

show();
```

Output (Browser)

```
Window Object
```

---

With Strict Mode

```javascript
"use strict";

function show() {
    console.log(this);
}

show();
```

Output

```
undefined
```

---

# Rule 6: Read-Only Properties Cannot Be Changed

```javascript
"use strict";

const person = {};

Object.defineProperty(person, "name", {
    value: "Niket",
    writable: false
});

person.name = "Rahul";
```

Output

```
TypeError
```

---

# Rule 7: Old Octal Numbers Are Not Allowed

Wrong:

```javascript
"use strict";

let number = 010;
```

Output

```
SyntaxError
```

Correct:

```javascript
let number = 10;
```

---

# Example Without Strict Mode

```javascript
function student() {

    age = 20;

    console.log(age);
}

student();
```

Output

```
20
```

Problem:

- Forgot to write `let`
- Global variable created
- Hard to debug

---

# Example With Strict Mode

```javascript
"use strict";

function student() {

    age = 20;

    console.log(age);
}

student();
```

Output

```
ReferenceError: age is not defined
```

Strict Mode immediately catches the mistake.

---

# Real-Life Example

Without Strict Mode

```javascript
username = "Niket";

function login() {
    console.log(username);
}

login();
```

Works, but creates a global variable.

---

With Strict Mode

```javascript
"use strict";

username = "Niket";
```

Output

```
ReferenceError
```

Correct

```javascript
"use strict";

let username = "Niket";

function login() {
    console.log(username);
}

login();
```

Output

```
Niket
```

---

# Why Developers Use Strict Mode

- Finds mistakes early.
- Prevents accidental global variables.
- Makes code safer.
- Makes debugging easier.
- Improves code quality.
- Encourages best coding practices.
- Makes JavaScript more secure.

---

# Is `"use strict"` Needed in ES6 Modules?

No.

If you use **ES Modules** (`import` / `export`), Strict Mode is enabled automatically.

Example:

```javascript
// user.js
export const name = "Niket";
```

```javascript
// app.js
import { name } from "./user.js";
```

You do not need to write:

```javascript
"use strict";
```

---

# Advantages

✅ Finds coding mistakes early

✅ Prevents accidental global variables

✅ Makes debugging easier

✅ Makes code safer

✅ Improves performance in some JavaScript engines

✅ Encourages clean coding

---

# Disadvantages

❌ Older JavaScript code may stop working

❌ Some old coding techniques are not allowed

❌ Beginners may see more errors until they learn the rules

---

# Strict Mode vs Normal Mode

| Normal JavaScript | Strict Mode |
|-------------------|------------|
| Allows undeclared variables | Throws ReferenceError |
| Allows duplicate parameters | Throws SyntaxError |
| `this` points to Window object | `this` becomes undefined |
| Silent errors | Shows real errors |
| Easier to make mistakes | Safer and cleaner code |

---

# Best Practices

✔ Always write `"use strict";` at the top of normal JavaScript files.

✔ Always declare variables using `let`, `const`, or `var`.

✔ Prefer `const` whenever the value should not change.

✔ Avoid global variables.

✔ Use meaningful variable names.

✔ Fix every Strict Mode error instead of disabling it.

---

# Interview Questions

### 1. What is Strict Mode?

Strict Mode is a JavaScript feature introduced in ES5 that helps developers write safer and cleaner code by catching common mistakes.

---

### 2. How do you enable Strict Mode?

```javascript
"use strict";
```

---

### 3. What happens if you use an undeclared variable in Strict Mode?

It throws a **ReferenceError**.

---

### 4. Can duplicate function parameters be used?

No.

Strict Mode throws a **SyntaxError**.

---

### 5. What is the value of `this` inside a normal function in Strict Mode?

```
undefined
```

---

### 6. Is Strict Mode enabled automatically in ES Modules?

Yes.

All ES Modules automatically run in Strict Mode.

---

### 7. What are the main advantages of Strict Mode?

- Prevents accidental global variables
- Finds bugs early
- Makes debugging easier
- Improves code quality
- Makes JavaScript safer

---

# Common Errors in Strict Mode

| Error | Reason |
|--------|--------|
| ReferenceError | Variable not declared |
| SyntaxError | Duplicate parameters or invalid syntax |
| TypeError | Modifying read-only property |

---

# Summary

- `"use strict"` enables Strict Mode.
- Introduced in **ES5**.
- Helps write safer, cleaner, and more reliable JavaScript.
- Prevents many common mistakes.
- Converts silent errors into actual errors.
- Makes debugging much easier.
- ES Modules automatically use Strict Mode.
- Using Strict Mode is considered a best practice in modern JavaScript.