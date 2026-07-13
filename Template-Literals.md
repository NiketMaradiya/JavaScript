# Template Literals in JavaScript (ES6)

## What are Template Literals?

Template Literals are a modern way to create strings in JavaScript.

They were introduced in **ES6 (ECMAScript 2015)**.

Instead of using **single quotes (' ')** or **double quotes (" ")**, Template Literals use **backticks (` `)**.

They make it easy to:

- Insert variables into strings
- Write multiline strings
- Use JavaScript expressions inside strings
- Make code cleaner and easier to read

---

# Syntax

```javascript
`Your Text Here`
```

Example:

```javascript
let message = `Hello World`;

console.log(message);
```

Output

```
Hello World
```

---

# Why Use Template Literals?

Without Template Literals:

```javascript
let name = "Niket";

console.log("Hello " + name);
```

Output

```
Hello Niket
```

With Template Literals:

```javascript
let name = "Niket";

console.log(`Hello ${name}`);
```

Output

```
Hello Niket
```

✅ Cleaner Code

✅ No `+` Operator

✅ Easy to Read

---

# Backticks (`)

Template Literals always use **backticks**.

Example

```javascript
`Hello`
```

Not

```javascript
"Hello"
```

or

```javascript
'Hello'
```

---

# Variable Interpolation

Interpolation means inserting a variable inside a string.

Syntax

```javascript
${variableName}
```

Example

```javascript
let name = "Niket";

console.log(`Welcome ${name}`);
```

Output

```
Welcome Niket
```

---

# Multiple Variables

```javascript
let firstName = "Niket";
let lastName = "Maradiya";

console.log(`Full Name: ${firstName} ${lastName}`);
```

Output

```
Full Name: Niket Maradiya
```

---

# Numbers Inside Template Literals

```javascript
let age = 21;

console.log(`Age: ${age}`);
```

Output

```
Age: 21
```

---

# Boolean Values

```javascript
let isStudent = true;

console.log(`Student: ${isStudent}`);
```

Output

```
Student: true
```

---

# JavaScript Expressions

Anything inside `${}` is treated as JavaScript code.

Example

```javascript
console.log(`2 + 3 = ${2 + 3}`);
```

Output

```
2 + 3 = 5
```

---

Example

```javascript
let a = 20;
let b = 30;

console.log(`Sum = ${a + b}`);
```

Output

```
Sum = 50
```

---

# Function Inside Template Literals

```javascript
function greet(name) {
    return `Hello ${name}`;
}

console.log(`${greet("Niket")}`);
```

Output

```
Hello Niket
```

---

# Method Inside Template Literals

```javascript
let name = "niket";

console.log(`Uppercase: ${name.toUpperCase()}`);
```

Output

```
Uppercase: NIKET
```

---

# Ternary Operator

```javascript
let marks = 80;

console.log(`Result: ${marks >= 35 ? "Pass" : "Fail"}`);
```

Output

```
Result: Pass
```

---

# Multiline Strings

Without Template Literals

```javascript
let text = "Hello\nWelcome\nJavaScript";

console.log(text);
```

Output

```
Hello
Welcome
JavaScript
```

With Template Literals

```javascript
let text = `
Hello
Welcome
JavaScript
`;

console.log(text);
```

Output

```
Hello
Welcome
JavaScript
```

No need to use `\n`.

---

# HTML Example

```javascript
let name = "Niket";

let html = `
<h1>${name}</h1>
<p>Welcome to JavaScript</p>
`;

console.log(html);
```

Output

```html
<h1>Niket</h1>
<p>Welcome to JavaScript</p>
```

---

# Invoice Example

```javascript
let product = "Laptop";
let price = 50000;
let quantity = 2;

console.log(`
Product : ${product}
Price   : ₹${price}
Quantity: ${quantity}
Total   : ₹${price * quantity}
`);
```

Output

```
Product : Laptop
Price   : ₹50000
Quantity: 2
Total   : ₹100000
```

---

# Student Report Example

```javascript
let name = "Rahul";
let marks = 88;

console.log(`
Student : ${name}
Marks   : ${marks}
Grade   : ${marks >= 90 ? "A" : "B"}
`);
```

Output

```
Student : Rahul
Marks   : 88
Grade   : B
```

---

# Shopping Bill Example

```javascript
let item = "Mobile";
let price = 18000;
let discount = 2000;

console.log(`
Item      : ${item}
Price     : ₹${price}
Discount  : ₹${discount}
Pay       : ₹${price - discount}
`);
```

Output

```
Item      : Mobile
Price     : ₹18000
Discount  : ₹2000
Pay       : ₹16000
```

---

# Object Example

```javascript
let user = {
    name: "Niket",
    city: "Ahmedabad",
    age: 21
};

console.log(`
Name : ${user.name}
City : ${user.city}
Age  : ${user.age}
`);
```

Output

```
Name : Niket
City : Ahmedabad
Age  : 21
```

---

# Memory Representation

```javascript
let name = "Niket";
let age = 21;

let message = `Hello ${name}, Age ${age}`;
```

Memory

```
name
 ↓
"Niket"

age
 ↓
21

message
 ↓
"Hello Niket, Age 21"
```

---

# Common Mistakes

## 1. Using Single Quotes

❌ Wrong

```javascript
let name = "Niket";

console.log('Hello ${name}');
```

Output

```
Hello ${name}
```

✅ Correct

```javascript
console.log(`Hello ${name}`);
```

Output

```
Hello Niket
```

---

## 2. Forgetting `${}`

❌ Wrong

```javascript
let age = 20;

console.log(`Age age`);
```

Output

```
Age age
```

✅ Correct

```javascript
console.log(`Age ${age}`);
```

Output

```
Age 20
```

---

## 3. Missing Closing Brace

❌ Wrong

```javascript
console.log(`Hello ${name`);
```

Syntax Error

✅ Correct

```javascript
console.log(`Hello ${name}`);
```

---

# Advantages

- Easy to read
- No `+` operator needed
- Supports variables
- Supports expressions
- Supports function calls
- Supports multiline strings
- Cleaner HTML generation
- Used in React, Node.js, Express, and modern JavaScript

---

# Disadvantages

- Works only in ES6 and newer versions.
- Beginners often forget to use backticks instead of quotes.

---

# Difference Between Normal Strings and Template Literals

| Normal String | Template Literal |
|--------------|------------------|
| Uses `' '` or `" "` | Uses `` ` ` `` |
| Uses `+` | Uses `${}` |
| Difficult to read | Easy to read |
| No direct multiline support | Supports multiline |
| Limited | More powerful |

---

# Real-Life Uses

- Welcome Messages
- Invoice Generation
- Email Templates
- HTML Templates
- React JSX
- Express Responses
- Report Cards
- Shopping Bills
- API Responses

---

# Interview Questions

### 1. What are Template Literals?

Template Literals are strings created using backticks (` `). They support variable interpolation, multiline strings, and expressions.

---

### 2. Which JavaScript version introduced Template Literals?

**Answer:** ES6 (ECMAScript 2015)

---

### 3. Which symbol is used for Template Literals?

**Answer:** Backticks (` `)

---

### 4. What is String Interpolation?

Using `${}` to insert variables or expressions inside a string.

Example

```javascript
let name = "Niket";

console.log(`Hello ${name}`);
```

---

### 5. Can JavaScript expressions be used inside Template Literals?

Yes.

```javascript
console.log(`${10 + 20}`);
```

Output

```
30
```

---

### 6. Can functions be called inside Template Literals?

Yes.

```javascript
function add(a, b) {
    return a + b;
}

console.log(`Sum = ${add(10,20)}`);
```

Output

```
Sum = 30
```

---

### 7. Why are Template Literals better than String Concatenation?

- Cleaner syntax
- Easier to read
- Supports variables
- Supports expressions
- Supports multiline strings
- Less code

---

# Summary

- Template Literals were introduced in **ES6**.
- They use **backticks (` `)** instead of quotes.
- `${}` is used to insert variables and expressions.
- They support **multiline strings** without using `\n`.
- They make code **shorter, cleaner, and easier to maintain**.
- They are widely used in **React, Node.js, Express, and modern JavaScript development**.