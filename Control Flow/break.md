# JavaScript `break` Statement

---

# What is `break`?

The `break` statement is used to **stop a loop or a switch statement immediately**.

When JavaScript reaches a `break` statement, it exits the loop and continues executing the code after the loop.

Think of it like an **Emergency Exit**.

Imagine you are searching for your friend in a classroom.

As soon as you find your friend, you stop searching.

That is exactly what `break` does.

---

# Syntax

```javascript
break;
```

---

# Flow Diagram

```
Start Loop
    │
    ▼
Run Code
    │
    ▼
Condition True?
    │
 ┌──┴──┐
 │     │
No    Yes
 │     │
 ▼     ▼
Next  break
Loop    │
         ▼
     Exit Loop
```

---

# Example 1: Stop a Loop

```javascript
for (let i = 1; i <= 10; i++) {

    if (i === 5) {
        break;
    }

    console.log(i);
}
```

### Output

```
1
2
3
4
```

### Explanation

The loop starts from 1.

```
i = 1 → Print

i = 2 → Print

i = 3 → Print

i = 4 → Print

i = 5

Condition is true

↓

break

↓

Loop Ends
```

---

# Example 2: Find a Number

```javascript
for (let i = 1; i <= 10; i++) {

    if (i === 7) {
        console.log("Number Found");
        break;
    }

    console.log(i);
}
```

### Output

```
1
2
3
4
5
6
Number Found
```

### Explanation

The loop checks every number.

```
1 → Not Found

2 → Not Found

3 → Not Found

4 → Not Found

5 → Not Found

6 → Not Found

7 → Found

↓

break

↓

Loop Ends
```

---

# Example 3: while Loop

```javascript
let number = 1;

while (number <= 10) {

    if (number === 6) {
        break;
    }

    console.log(number);

    number++;
}
```

### Output

```
1
2
3
4
5
```

---

# Example 4: do...while Loop

```javascript
let i = 1;

do {

    if (i === 4) {
        break;
    }

    console.log(i);

    i++;

} while (i <= 10);
```

### Output

```
1
2
3
```

---

# Example 5: Infinite Loop

```javascript
let i = 1;

while (true) {

    console.log(i);

    if (i === 5) {
        break;
    }

    i++;
}
```

### Output

```
1
2
3
4
5
```

### Why use break?

Without `break`, this loop would run forever.

---

# Example 6: break in switch

```javascript
let day = 2;

switch (day) {

    case 1:
        console.log("Monday");
        break;

    case 2:
        console.log("Tuesday");
        break;

    case 3:
        console.log("Wednesday");
        break;

    default:
        console.log("Invalid");
}
```

### Output

```
Tuesday
```

---

# What Happens Without break?

```javascript
let day = 2;

switch (day) {

    case 1:
        console.log("Monday");

    case 2:
        console.log("Tuesday");

    case 3:
        console.log("Wednesday");

    default:
        console.log("Invalid");
}
```

### Output

```
Tuesday
Wednesday
Invalid
```

This happens because JavaScript continues executing the next cases.

This is called **Fall Through**.

---

# Example 7: Search in an Array

```javascript
let fruits = ["Apple", "Banana", "Mango", "Orange"];

for (let i = 0; i < fruits.length; i++) {

    if (fruits[i] === "Mango") {
        console.log("Fruit Found");
        break;
    }

    console.log(fruits[i]);
}
```

### Output

```
Apple
Banana
Fruit Found
```

---

# Example 8: Nested Loop

```javascript
for (let i = 1; i <= 3; i++) {

    for (let j = 1; j <= 5; j++) {

        if (j === 3) {
            break;
        }

        console.log(i, j);
    }
}
```

### Output

```
1 1
1 2
2 1
2 2
3 1
3 2
```

### Explanation

Only the **inner loop** stops.

The outer loop continues.

---

# Real-Life Example

Imagine you are searching for your car in a parking lot.

```
Parking Slot 1

↓

Not Found

↓

Parking Slot 2

↓

Not Found

↓

Parking Slot 3

↓

Car Found

↓

break

↓

Go Home
```

There is no need to search the remaining parking slots.

---

# break vs continue

| break | continue |
|--------|----------|
| Stops the entire loop | Skips only one iteration |
| Loop ends immediately | Loop continues |
| Used to exit a loop | Used to skip current iteration |

### break Example

```javascript
for (let i = 1; i <= 5; i++) {

    if (i === 3) {
        break;
    }

    console.log(i);
}
```

Output

```
1
2
```

---

### continue Example

```javascript
for (let i = 1; i <= 5; i++) {

    if (i === 3) {
        continue;
    }

    console.log(i);
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

# When Should We Use break?

Use `break` when:

- You found the data you are searching for.
- You want to stop a loop early.
- You want to avoid unnecessary iterations.
- You want to stop an infinite loop.
- You want to stop a `switch` statement after one case.

---

# Common Mistakes

## 1. Forgetting break in switch

```javascript
switch(day){

    case 1:
        console.log("Monday");

    case 2:
        console.log("Tuesday");
}
```

Output

```
Monday
Tuesday
```

---

## 2. Thinking break stops every loop

```javascript
for (...) {

    for (...) {

        break;
    }

}
```

Only the inner loop stops.

---

# Interview Questions

## 1. What is break in JavaScript?

**Answer:**
`break` immediately exits a loop or switch statement.

---

## 2. Where can break be used?

**Answer:**

- for
- while
- do...while
- for...of
- for...in
- switch

---

## 3. What is the difference between break and continue?

**Answer:**

`break` stops the loop completely.

`continue` skips only the current iteration.

---

## 4. Can break be used outside a loop?

**Answer:**

No.

```javascript
break;
```

This produces a **Syntax Error**.

---

## 5. Does break stop nested loops?

**Answer:**

No.

It only stops the loop where it is written.

---

# Advantages of break

- Makes code faster.
- Avoids unnecessary loop iterations.
- Easy to exit when data is found.
- Improves performance.
- Makes code easier to understand.

---

# Disadvantages of break

- Too many `break` statements can make code harder to read.
- In nested loops, it only exits one loop.
- Incorrect use can stop the loop earlier than expected.

---

# Quick Revision

- `break` stops a loop immediately.
- It works with loops and switch statements.
- It exits the current loop.
- It prevents switch fall-through.
- It is useful for searching, validation, and infinite loops.
- `break` and `continue` are different.
- `break` ends the loop, while `continue` skips only one iteration.

---

# Practice Questions

### Question 1

Print numbers from 1 to 20 but stop when the number becomes 12.

---

### Question 2

Find the value **50** from an array using `break`.

---

### Question 3

Create an infinite `while(true)` loop and stop it after printing 10.

---

### Question 4

Create a switch statement for the months and use `break` correctly.

---

### Question 5

Use nested loops and observe that `break` only exits the inner loop.

---

# Summary

`break` is one of the most useful control statements in JavaScript. It allows you to stop loops and switch statements immediately when your goal is completed. Using `break` correctly makes your code faster, cleaner, and easier to maintain.