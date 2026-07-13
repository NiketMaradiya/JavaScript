# JavaScript `for...of` Loop

## What is `for...of`?

The **`for...of`** loop is used to iterate over the **values** of an iterable object.

It works with:

* Arrays
* Strings
* Maps
* Sets
* NodeList
* TypedArray

> **Remember:** `for...of` gives the **value**, not the index.

---

# Syntax

```javascript
for (let variable of iterable) {
    // Code
}
```

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

Output

```
Apple
Banana
Mango
```

---

# How `for...of` Works

Array

```javascript
let numbers = [10, 20, 30];
```

Memory

```
Index     Value

0         10
1         20
2         30
```

Loop

```
Iteration 1
number = 10

Iteration 2
number = 20

Iteration 3
number = 30
```

---

# Example 1 - Print Array Values

```javascript
let fruits = ["Apple", "Banana", "Mango"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

Output

```
Apple
Banana
Mango
```

---

# Example 2 - Print String Characters

```javascript
let name = "Niket";

for (let letter of name) {
    console.log(letter);
}
```

Output

```
N
i
k
e
t
```

---

# Example 3 - Sum of Numbers

```javascript
let numbers = [10, 20, 30, 40];

let total = 0;

for (let number of numbers) {
    total += number;
}

console.log(total);
```

Output

```
100
```

---

# Example 4 - Find Even Numbers

```javascript
let numbers = [3, 6, 9, 12, 15, 18];

for (let number of numbers) {

    if (number % 2 === 0) {
        console.log(number);
    }

}
```

Output

```
6
12
18
```

---

# Example 5 - Calculate Average

```javascript
let marks = [80, 90, 70, 60];

let total = 0;

for (let mark of marks) {
    total += mark;
}

let average = total / marks.length;

console.log(average);
```

Output

```
75
```

---

# Example 6 - Using `break`

```javascript
let fruits = ["Apple", "Banana", "Mango", "Orange"];

for (let fruit of fruits) {

    if (fruit === "Mango") {
        break;
    }

    console.log(fruit);

}
```

Output

```
Apple
Banana
```

---

# Example 7 - Using `continue`

```javascript
let numbers = [1, 2, 3, 4, 5];

for (let number of numbers) {

    if (number === 3) {
        continue;
    }

    console.log(number);

}
```

Output

```
1
2
4
5
```

---

# Example 8 - Loop Through a Set

```javascript
let colors = new Set(["Red", "Green", "Blue"]);

for (let color of colors) {
    console.log(color);
}
```

Output

```
Red
Green
Blue
```

---

# Example 9 - Loop Through a Map

```javascript
let student = new Map([
    ["name", "Niket"],
    ["age", 21],
    ["city", "Ahmedabad"]
]);

for (let [key, value] of student) {
    console.log(key, value);
}
```

Output

```
name Niket
age 21
city Ahmedabad
```

---

# Example 10 - Array of Objects

```javascript
let students = [
    { name: "Niket", marks: 90 },
    { name: "Rahul", marks: 85 },
    { name: "Priya", marks: 95 }
];

for (let student of students) {
    console.log(student.name, student.marks);
}
```

Output

```
Niket 90
Rahul 85
Priya 95
```

---

# `for...of` vs `for...in`

```javascript
let fruits = ["Apple", "Banana", "Mango"];
```

### `for...of`

```javascript
for (let fruit of fruits) {
    console.log(fruit);
}
```

Output

```
Apple
Banana
Mango
```

### `for...in`

```javascript
for (let index in fruits) {
    console.log(index);
}
```

Output

```
0
1
2
```

| `for...of`                           | `for...in`                |
| ------------------------------------ | ------------------------- |
| Returns values                       | Returns keys/indexes      |
| Used for Arrays, Strings, Maps, Sets | Mostly used for Objects   |
| Easy to read                         | Used when keys are needed |

---

# Advantages

* Easy to read
* Gives values directly
* No need to use indexes
* Works with Arrays, Strings, Maps, Sets, and more
* Cleaner code than a traditional `for` loop

---

# Disadvantages

* Does not return the index
* Cannot be used directly on plain objects
* Less flexible than a traditional `for` loop for index-based logic

---

# Common Mistake

❌ Wrong

```javascript
let person = {
    name: "Niket",
    age: 21
};

for (let value of person) {
    console.log(value);
}
```

Output

```
TypeError: person is not iterable
```

✅ Correct

```javascript
for (let key in person) {
    console.log(key, person[key]);
}
```

Or

```javascript
for (let [key, value] of Object.entries(person)) {
    console.log(key, value);
}
```

---

# Real-World Example

Shopping Cart

```javascript
let cart = [
    "Laptop",
    "Mouse",
    "Keyboard",
    "Headphones"
];

for (let item of cart) {
    console.log("Product:", item);
}
```

Output

```
Product: Laptop
Product: Mouse
Product: Keyboard
Product: Headphones
```

---

# Interview Questions

### 1. What is `for...of` in JavaScript?

**Answer:** It is a loop used to iterate over the values of iterable objects like arrays, strings, maps, and sets.

---

### 2. Does `for...of` return the index?

**Answer:** No. It returns the value.

---

### 3. Can `for...of` be used with objects?

**Answer:** No. Plain objects are not iterable. Use `for...in` or `Object.entries()`.

---

### 4. What data types support `for...of`?

* Arrays
* Strings
* Maps
* Sets
* NodeList
* TypedArray

---

### 5. Difference between `for...of` and `for...in`?

| `for...of`                 | `for...in`               |
| -------------------------- | ------------------------ |
| Returns values             | Returns keys/indexes     |
| Used with iterable objects | Mainly used with objects |

---

# Quick Revision

* `for...of` loops through **values**.
* Best for Arrays and Strings.
* Does **not** return indexes.
* Works with iterable objects.
* Cannot be used directly on plain objects.
* Use `break` and `continue` inside `for...of`.
* Simple, clean, and beginner-friendly.
