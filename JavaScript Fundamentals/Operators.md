# JavaScript Operators

Operators are symbols that perform operations on values or variables.

Example:

```javascript
let result = 10 + 5;

console.log(result);
```

Output

```
15
```

---

# Types of Operators

1. Arithmetic Operators
2. Assignment Operators
3. Comparison Operators
4. Logical Operators
5. Increment & Decrement Operators
6. String Operators
7. Ternary Operator
8. Nullish Coalescing Operator (??)
9. Optional Chaining Operator (?.)
10. Type Operators
11. Bitwise Operators

---

# 1. Arithmetic Operators

Used for mathematical calculations.

| Operator | Meaning | Example |
|----------|---------|---------|
| + | Addition | 10 + 5 |
| - | Subtraction | 10 - 5 |
| * | Multiplication | 10 * 5 |
| / | Division | 10 / 5 |
| % | Remainder | 10 % 3 |
| ** | Power | 2 ** 3 |

Example

```javascript
let a = 20;
let b = 5;

console.log(a + b);
console.log(a - b);
console.log(a * b);
console.log(a / b);
console.log(a % b);
console.log(2 ** 4);
```

Output

```
25
15
100
4
0
16
```

---

# 2. Assignment Operators

Used to assign values.

| Operator | Example | Same As |
|----------|---------|---------|
| = | x = 10 | Assign value |
| += | x += 5 | x = x + 5 |
| -= | x -= 5 | x = x - 5 |
| *= | x *= 5 | x = x * 5 |
| /= | x /= 5 | x = x / 5 |
| %= | x %= 5 | x = x % 5 |
| **= | x **= 2 | x = x ** 2 |

Example

```javascript
let x = 10;

x += 5;

console.log(x);
```

Output

```
15
```

---

# 3. Comparison Operators

Compare two values and return true or false.

| Operator | Meaning |
|----------|---------|
| == | Equal |
| === | Strict Equal |
| != | Not Equal |
| !== | Strict Not Equal |
| > | Greater Than |
| < | Less Than |
| >= | Greater Than or Equal |
| <= | Less Than or Equal |

Example

```javascript
console.log(10 == "10");
console.log(10 === "10");
console.log(10 > 5);
console.log(10 <= 5);
```

Output

```
true
false
true
false
```

**Difference**

`==`

Checks only value.

`===`

Checks value and datatype.

Always use **===** in modern JavaScript.

---

# 4. Logical Operators

| Operator | Meaning |
|----------|---------|
| && | AND |
| || | OR |
| ! | NOT |

Example

```javascript
let age = 20;
let hasLicense = true;

console.log(age >= 18 && hasLicense);
```

Output

```
true
```

---

# 5. Increment & Decrement

Increment increases value by 1.

```javascript
let x = 5;

x++;

console.log(x);
```

Output

```
6
```

Decrement decreases value by 1.

```javascript
let x = 5;

x--;

console.log(x);
```

Output

```
4
```

### Prefix

```javascript
let x = 5;

console.log(++x);
```

Output

```
6
```

### Postfix

```javascript
let x = 5;

console.log(x++);
console.log(x);
```

Output

```
5
6
```

---

# 6. String Operator

The `+` operator joins strings.

```javascript
let firstName = "Niket";
let lastName = "Maradiya";

console.log(firstName + " " + lastName);
```

Output

```
Niket Maradiya
```

---

# 7. Ternary Operator

Short form of if...else.

Syntax

```javascript
condition ? value1 : value2;
```

Example

```javascript
let age = 20;

let result = age >= 18 ? "Adult" : "Minor";

console.log(result);
```

Output

```
Adult
```

---

# 8. Nullish Coalescing Operator (??)

Returns the right value only when the left value is **null** or **undefined**.

```javascript
let username = null;

console.log(username ?? "Guest");
```

Output

```
Guest
```

---

# 9. Optional Chaining (?.)

Safely accesses object properties.

```javascript
let user = {
    name: "Niket"
};

console.log(user.address?.city);
```

Output

```
undefined
```

---

# 10. Type Operators

### typeof

```javascript
console.log(typeof 100);
console.log(typeof "Hello");
console.log(typeof true);
```

Output

```
number
string
boolean
```

### instanceof

```javascript
let arr = [];

console.log(arr instanceof Array);
```

Output

```
true
```

---

# 11. Bitwise Operators

Advanced operators that work with binary numbers.

```javascript
console.log(5 & 1);
console.log(5 | 1);
console.log(5 ^ 1);
console.log(~5);
console.log(5 << 1);
console.log(5 >> 1);
```

---

# Real World Example

```javascript
let age = 22;
let hasID = true;
let country = "India";

if (age >= 18 && hasID && country === "India") {
    console.log("You can Vote");
} else {
    console.log("You cannot Vote");
}
```

Output

```
You can Vote
```

---

# Common Mistakes

❌ Wrong

```javascript
if (x = 10) {
    console.log("Hello");
}
```

✅ Correct

```javascript
if (x === 10) {
    console.log("Hello");
}
```

---

# Interview Questions

## Basic

1. What is an operator in JavaScript?
2. What are the different types of operators?
3. What is the difference between == and ===?
4. What is the difference between = and ===?
5. What is the modulus (%) operator?
6. What is the difference between ++x and x++?
7. What is typeof?
8. What is instanceof?
9. What is optional chaining?
10. What is the ternary operator?

## Intermediate

11. Why should we use === instead of ==?
12. Explain operator precedence.
13. Difference between && and ||?
14. Difference between || and ???
15. What is the output of 10 + "5"?
16. What is the output of "5" - 2?
17. What is the output of true && false || true?
18. When should we use optional chaining?
19. Explain assignment operators with examples.
20. Explain comparison operators with examples.

---

# Quick Revision

| Category | Operators |
|----------|-----------|
| Arithmetic | + - * / % ** |
| Assignment | = += -= *= /= %= **= |
| Comparison | == === != !== > < >= <= |
| Logical | && || ! |
| Increment / Decrement | ++ -- |
| String | + |
| Ternary | ?: |
| Nullish | ?? |
| Optional Chaining | ?. |
| Type | typeof, instanceof |
| Bitwise | &, \|, ^, ~, <<, >> |