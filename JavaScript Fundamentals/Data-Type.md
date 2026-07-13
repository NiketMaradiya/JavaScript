# JavaScript Data Types

## What is Data?

Data means information.

Examples:

* Name
* Age
* Mobile Number
* Email
* Salary

Example:

```javascript
let name = "Niket";
let age = 21;
let isStudent = true;
```

Here,

```text
"Niket"
21
true
```

are data.

---

# What is a Data Type?

A Data Type tells JavaScript what kind of value is stored in a variable.

Example:

```javascript
let name = "Niket";
let age = 21;
```

JavaScript understands:

```text
name → String
age  → Number
```

---

# Why Do We Need Data Types?

JavaScript needs to know whether the value is text, number, or something else.

Example:

```javascript
console.log(10 + 5);
```

Output

```text
15
```

```javascript
console.log("10" + 5);
```

Output

```text
105
```

Reason:

```text
10   → Number
"10" → String
```

---

# JavaScript Data Types

JavaScript has 8 main Data Types.

```text
1. String
2. Number
3. BigInt
4. Boolean
5. Undefined
6. Null
7. Symbol
8. Object
```

---

# Categories

```text
Primitive

String
Number
BigInt
Boolean
Undefined
Null
Symbol

-------------------

Reference

Object
Array
Function
Date
```

---

# 1. String

A String stores text.

Example

```javascript
let name = "Niket";

console.log(name);
```

Output

```text
Niket
```

Check type

```javascript
console.log(typeof name);
```

Output

```text
string
```

Real Example

```javascript
let city = "Ahmedabad";
let company = "Google";
```

Common Mistake

```javascript
let age = "20";
```

This is a **String**, not a Number.

---

# 2. Number

A Number stores numeric values.

Example

```javascript
let marks = 95;
let salary = 50000;
let price = 499.99;
```

Check type

```javascript
console.log(typeof marks);
```

Output

```text
number
```

Calculation

```javascript
let a = 20;
let b = 10;

console.log(a + b);
```

Output

```text
30
```

---

# 3. BigInt

BigInt stores very large numbers.

Example

```javascript
let population = 12345678901234567890n;

console.log(population);
```

Output

```text
12345678901234567890n
```

Check type

```javascript
console.log(typeof population);
```

Output

```text
bigint
```

---

# Memory Example

```javascript
let name = "Niket";
let age = 21;
```

```text
Memory

+---------+
| name    |
| "Niket" |
+---------+

+---------+
| age     |
| 21      |
+---------+
```

---

# Quick Revision

| Data Type | Example   | typeof |
| --------- | --------- | ------ |
| String    | `"Niket"` | string |
| Number    | `21`      | number |
| BigInt    | `100n`    | bigint |

---

# Practice

```javascript
let student = "Rahul";
let marks = 90;
let stars = 999999999999999999n;

console.log(typeof student);
console.log(typeof marks);
console.log(typeof stars);
```

Output

```text
string
number
bigint
```

---

# Interview Questions

1. What is a Data Type?
2. How many Data Types are in JavaScript?
3. What is a String?
4. What is a Number?
5. What is BigInt?
6. What is the `typeof` operator?

---

# Summary

* Data means information.
* A Data Type tells JavaScript what kind of value is stored.
* String stores text.
* Number stores numeric values.
* BigInt stores very large numbers.
* Use `typeof` to check the data type.
