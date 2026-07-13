# JavaScript `continue` Statement

The `continue` statement is used inside loops.

It **skips the current iteration** (current loop cycle) and immediately moves to the **next iteration**.

Unlike `break`, it **does not stop the loop**.

---

# Syntax

```javascript
continue;
```

It can be used inside:

- for
- while
- do...while
- for...of
- for...in

---

# Difference Between `break` and `continue`

| break | continue |
|-------|----------|
| Stops the loop completely | Skips only the current iteration |
| Loop ends immediately | Loop continues with the next iteration |
| Used when you want to exit the loop | Used when you want to ignore one iteration |

---

# Example 1: Basic Example

```javascript
for (let i = 1; i <= 5; i++) {

    if (i === 3) {
        continue;
    }

    console.log(i);
}
```

### Output

```
1
2
4
5
```

### Explanation

Iteration 1

```
i = 1

Condition false

Print 1
```

Iteration 2

```
i = 2

Condition false

Print 2
```

Iteration 3

```
i = 3

Condition true

continue

Skip console.log()
```

Iteration 4

```
i = 4

Print 4
```

Iteration 5

```
i = 5

Print 5
```

---

# Memory Flow

```
i = 1 → Print

i = 2 → Print

i = 3 → Skip

i = 4 → Print

i = 5 → Print
```

---

# Example 2: Print Only Odd Numbers

```javascript
for (let i = 1; i <= 10; i++) {

    if (i % 2 === 0) {
        continue;
    }

    console.log(i);
}
```

### Output

```
1
3
5
7
9
```

### Explanation

```
2 Skip

4 Skip

6 Skip

8 Skip

10 Skip
```

Only odd numbers are printed.

---

# Example 3: Print Only Even Numbers

```javascript
for (let i = 1; i <= 10; i++) {

    if (i % 2 !== 0) {
        continue;
    }

    console.log(i);
}
```

### Output

```
2
4
6
8
10
```

---

# Example 4: Skip One Student

```javascript
const students = [
    "Rahul",
    "Amit",
    "Neha",
    "Priya"
];

for (let i = 0; i < students.length; i++) {

    if (students[i] === "Neha") {
        continue;
    }

    console.log(students[i]);
}
```

### Output

```
Rahul
Amit
Priya
```

---

# Example 5: Skip Failed Students

```javascript
const marks = [90, 45, 78, 30, 88];

for (let i = 0; i < marks.length; i++) {

    if (marks[i] < 50) {
        continue;
    }

    console.log(marks[i]);
}
```

### Output

```
90
78
88
```

Students who scored below 50 are skipped.

---

# Example 6: continue in while Loop

```javascript
let i = 0;

while (i < 5) {

    i++;

    if (i === 3) {
        continue;
    }

    console.log(i);
}
```

### Output

```
1
2
4
5
```

### Why `i++` Comes First?

Correct

```javascript
let i = 0;

while (i < 5) {

    i++;

    if (i === 3) {
        continue;
    }

    console.log(i);
}
```

Wrong

```javascript
let i = 0;

while (i < 5) {

    if (i === 3) {
        continue;
    }

    i++;
}
```

When `i` becomes 3

```
continue

↓

i++ never executes

↓

i stays 3

↓

Infinite Loop
```

---

# Example 7: continue in for...of

```javascript
const fruits = [
    "Apple",
    "Banana",
    "Mango",
    "Orange"
];

for (const fruit of fruits) {

    if (fruit === "Mango") {
        continue;
    }

    console.log(fruit);
}
```

### Output

```
Apple
Banana
Orange
```

---

# Example 8: Skip Negative Numbers

```javascript
const numbers = [10, -5, 20, -8, 50];

for (const num of numbers) {

    if (num < 0) {
        continue;
    }

    console.log(num);
}
```

### Output

```
10
20
50
```

---

# Example 9: Skip Empty Strings

```javascript
const names = [
    "John",
    "",
    "Alex",
    "",
    "David"
];

for (const name of names) {

    if (name === "") {
        continue;
    }

    console.log(name);
}
```

### Output

```
John
Alex
David
```

---

# Real-World Example

Suppose you have an online shopping website.

Some products are out of stock.

```javascript
const products = [
    "Laptop",
    "Out of Stock",
    "Keyboard",
    "Mouse"
];

for (const product of products) {

    if (product === "Out of Stock") {
        continue;
    }

    console.log("Buy:", product);
}
```

### Output

```
Buy: Laptop
Buy: Keyboard
Buy: Mouse
```

The unavailable product is skipped.

---

# Common Mistakes

## Mistake 1

Using `continue` outside a loop.

```javascript
continue;
```

Output

```
SyntaxError
```

---

## Mistake 2

Infinite Loop

```javascript
let i = 0;

while (i < 5) {

    if (i === 2) {
        continue;
    }

    i++;
}
```

`i` never changes when it becomes 2.

The loop runs forever.

---

# When to Use continue

Use `continue` when you want to:

- Skip invalid data
- Skip duplicate values
- Ignore empty strings
- Ignore negative numbers
- Skip failed students
- Skip banned users
- Skip unavailable products
- Ignore unwanted records

---

# Interview Questions

## 1. What is the `continue` statement?

**Answer:**

It skips the current iteration of a loop and starts the next iteration.

---

## 2. Does `continue` stop the loop?

**Answer:**

No.

It only skips one iteration.

---

## 3. What is the difference between `break` and `continue`?

**Answer:**

`break` ends the loop.

`continue` skips only the current iteration.

---

## 4. Can `continue` be used in a while loop?

**Answer:**

Yes.

Be careful to update the loop variable, otherwise an infinite loop can occur.

---

## 5. Can `continue` be used outside a loop?

**Answer:**

No.

It throws a `SyntaxError`.

---

# Best Practices

- Use `continue` only when it makes your code easier to read.
- Avoid using too many `continue` statements in a single loop.
- Always update the loop variable in `while` loops before `continue`.
- Prefer clear conditions over complex nested `continue` statements.

---

# Summary

- `continue` skips the current iteration.
- It does **not** stop the loop.
- The loop continues with the next iteration.
- It works with `for`, `while`, `do...while`, `for...of`, and `for...in`.
- It is useful for ignoring unwanted data while processing the rest.

---

# Quick Revision

✅ Skips current iteration

✅ Does not stop the loop

✅ Moves to next iteration

✅ Works inside all loops

✅ Useful for filtering data during looping

❌ Cannot be used outside a loop

❌ Can cause an infinite loop in `while` if the loop variable is not updated