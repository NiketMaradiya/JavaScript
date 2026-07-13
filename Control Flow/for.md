# JavaScript `for` Loop

A complete beginner-friendly guide with examples.

---

# What is a `for` Loop?

A **for loop** is used to execute the same block of code multiple times.

Instead of writing the same code again and again, you can use a `for` loop.

### Without Loop

```javascript
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
```

Output

```
Hello
Hello
Hello
Hello
Hello
```

This works, but it is repetitive.

---

### With `for` Loop

```javascript
for (let i = 1; i <= 5; i++) {
    console.log("Hello");
}
```

Output

```
Hello
Hello
Hello
Hello
Hello
```

The loop repeats the code automatically.

---

# Why Do We Use a `for` Loop?

Imagine you want to print numbers from **1 to 1000**.

Without a loop, you would need to write 1000 `console.log()` statements.

Using a `for` loop:

```javascript
for (let i = 1; i <= 1000; i++) {
    console.log(i);
}
```

The loop does all the work for you.

---

# Syntax

```javascript
for (initialization; condition; update) {
    // Code to execute
}
```

Example

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

---

# Understanding Each Part

## 1. Initialization

```javascript
let i = 1;
```

- Creates the loop variable.
- Runs only once.

Memory

```
i → 1
```

---

## 2. Condition

```javascript
i <= 5
```

The condition is checked before every iteration.

```
1 <= 5 ✔
2 <= 5 ✔
3 <= 5 ✔
4 <= 5 ✔
5 <= 5 ✔
6 <= 5 ✖ Stop
```

---

## 3. Update

```javascript
i++
```

Equivalent to:

```javascript
i = i + 1;
```

Each iteration increases `i` by 1.

```
1 → 2 → 3 → 4 → 5 → 6
```

---

# How a `for` Loop Works

```javascript
for (let i = 1; i <= 3; i++) {
    console.log(i);
}
```

### Step 1

```
i = 1
Condition: 1 <= 3 ✔
Print: 1
Update: i = 2
```

Output

```
1
```

---

### Step 2

```
i = 2
Condition: 2 <= 3 ✔
Print: 2
Update: i = 3
```

Output

```
1
2
```

---

### Step 3

```
i = 3
Condition: 3 <= 3 ✔
Print: 3
Update: i = 4
```

Output

```
1
2
3
```

---

### Step 4

```
i = 4
Condition: 4 <= 3 ✖
Loop Stops
```

---

# Memory Diagram

```
Start

i = 1

↓

Print 1

↓

i = 2

↓

Print 2

↓

i = 3

↓

Print 3

↓

i = 4

↓

Condition False

↓

End
```

---

# Example 1: Print Numbers 1 to 5

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

Output

```
1
2
3
4
5
```

---

# Example 2: Print Even Numbers

```javascript
for (let i = 2; i <= 10; i += 2) {
    console.log(i);
}
```

Output

```
2
4
6
8
10
```

---

# Example 3: Print Odd Numbers

```javascript
for (let i = 1; i <= 10; i += 2) {
    console.log(i);
}
```

Output

```
1
3
5
7
9
```

---

# Example 4: Reverse Counting

```javascript
for (let i = 10; i >= 1; i--) {
    console.log(i);
}
```

Output

```
10
9
8
7
6
5
4
3
2
1
```

---

# Example 5: Multiplication Table

```javascript
let number = 5;

for (let i = 1; i <= 10; i++) {
    console.log(number + " x " + i + " = " + number * i);
}
```

Output

```
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

---

# Example 6: Sum of Numbers

```javascript
let sum = 0;

for (let i = 1; i <= 5; i++) {
    sum += i;
}

console.log(sum);
```

Output

```
15
```

Explanation

```
0 + 1 = 1
1 + 2 = 3
3 + 3 = 6
6 + 4 = 10
10 + 5 = 15
```

---

# Real-World Example

Print student roll numbers.

```javascript
for (let roll = 1; roll <= 5; roll++) {
    console.log("Student Roll:", roll);
}
```

Output

```
Student Roll: 1
Student Roll: 2
Student Roll: 3
Student Roll: 4
Student Roll: 5
```

---

# Infinite Loop

```javascript
for (let i = 1; i <= 5;) {
    console.log(i);
}
```

Output

```
1
1
1
1
1
...
```

Reason:

The value of `i` never changes because the update part is missing.

---

# Common Mistakes

## Missing Update

```javascript
for (let i = 1; i <= 5;) {
    console.log(i);
}
```

❌ Infinite loop.

---

## Wrong Condition

```javascript
for (let i = 5; i <= 1; i++) {
    console.log(i);
}
```

Output

```
Nothing
```

Reason:

The condition is false from the beginning.

---

# Best Practices

- Use `let` for loop variables.
- Keep the condition simple.
- Always update the loop variable.
- Avoid changing the loop variable manually inside the loop unless necessary.
- Write clean and readable code.

---

# When Should You Use a `for` Loop?

Use a `for` loop when:

- You know how many times the code should repeat.
- Printing numbers.
- Creating multiplication tables.
- Calculating totals.
- Processing arrays with indexes.
- Repeating tasks.

---

# Interview Questions

### 1. What is a `for` loop?

A `for` loop repeats a block of code until a condition becomes false.

---

### 2. How many parts does a `for` loop have?

Three:

- Initialization
- Condition
- Update

---

### 3. Which part runs only once?

Initialization.

---

### 4. Which part decides whether the loop continues?

Condition.

---

### 5. What happens if the condition is false initially?

The loop never executes.

---

### 6. What happens if the update expression is missing?

The loop may become an infinite loop.

---

### 7. Can all three expressions be omitted?

Yes, but you must ensure the loop ends using another mechanism (such as `break`).

---

### 8. Difference between `for` and `while`?

| for | while |
|------|--------|
| Best when the number of iterations is known | Best when the number of iterations is unknown |
| Initialization, condition, and update are together | Initialization and update are usually written separately |

---

# Practice Questions

### Easy

1. Print numbers from 1 to 20.
2. Print numbers from 20 to 1.
3. Print even numbers from 1 to 100.
4. Print odd numbers from 1 to 100.
5. Print your name 10 times.

---

### Medium

6. Find the sum of numbers from 1 to 100.
7. Print the multiplication table of 9.
8. Print all numbers divisible by 3.
9. Print all numbers divisible by 5.
10. Print squares of numbers from 1 to 10.

---

### Hard

11. Print this pattern:

```
*
**
***
****
*****
```

12. Print this pattern:

```
1
12
123
1234
12345
```

13. Print this pattern:

```
*****
****
***
**
*
```

---

# Summary

- A `for` loop repeats code multiple times.
- It has three parts:
  - Initialization
  - Condition
  - Update
- Initialization runs once.
- Condition is checked before every iteration.
- Update changes the loop variable after each iteration.
- The loop stops when the condition becomes false.
- `for` loops are useful for counting, calculations, patterns, and processing arrays.

---
