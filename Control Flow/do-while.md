# JavaScript `do...while` Loop

## What is `do...while`?

The `do...while` loop is a JavaScript loop that **executes the code first** and **checks the condition after**.

This means the code inside the loop will **always run at least one time**, even if the condition is `false`.

---

# Syntax

```javascript
do {
    // Code to execute
} while (condition);
```

---

# How `do...while` Works

```
        Start
          │
          ▼
   Execute Code
          │
          ▼
 Check Condition
          │
   ┌──────┴──────┐
   │             │
 True         False
   │             │
   ▼             ▼
Repeat         End
```

---

# Example 1: Print Numbers 1 to 5

```javascript
let i = 1;

do {
    console.log(i);
    i++;
} while (i <= 5);
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

# Step-by-Step Execution

### Initial Value

```javascript
i = 1
```

### First Iteration

```
Print 1
i becomes 2

Condition:
2 <= 5 ✔ True
```

### Second Iteration

```
Print 2
i becomes 3

Condition:
3 <= 5 ✔ True
```

### Third Iteration

```
Print 3
i becomes 4

Condition:
4 <= 5 ✔ True
```

### Fourth Iteration

```
Print 4
i becomes 5

Condition:
5 <= 5 ✔ True
```

### Fifth Iteration

```
Print 5
i becomes 6

Condition:
6 <= 5 ✖ False

Loop Ends
```

---

# Example 2: Condition is False

```javascript
let i = 10;

do {
    console.log(i);
} while (i < 5);
```

### Output

```
10
```

### Why?

The code executes **before** checking the condition.

---

# Example 3: Print Even Numbers

```javascript
let number = 2;

do {
    console.log(number);
    number += 2;
} while (number <= 10);
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

# Example 4: Multiplication Table of 5

```javascript
let i = 1;

do {
    console.log(`5 × ${i} = ${5 * i}`);
    i++;
} while (i <= 10);
```

### Output

```
5 × 1 = 5
5 × 2 = 10
5 × 3 = 15
...
5 × 10 = 50
```

---

# Example 5: Countdown

```javascript
let count = 5;

do {
    console.log(count);
    count--;
} while (count >= 1);
```

### Output

```
5
4
3
2
1
```

---

# Example 6: Sum of Numbers

```javascript
let i = 1;
let sum = 0;

do {
    sum += i;
    i++;
} while (i <= 5);

console.log(sum);
```

### Output

```
15
```

Calculation

```
1 + 2 + 3 + 4 + 5 = 15
```

---

# Example 7: Password Attempt

```javascript
let attempts = 1;

do {
    console.log("Checking Password...");
    attempts++;
} while (attempts <= 3);

console.log("Maximum attempts reached.");
```

### Output

```
Checking Password...
Checking Password...
Checking Password...
Maximum attempts reached.
```

---

# Example 8: Game Menu

```javascript
let playAgain = false;

do {
    console.log("Game Started");
} while (playAgain);
```

### Output

```
Game Started
```

The game starts once because `do...while` always runs at least one time.

---

# Memory Visualization

Initial

```
i → 1
```

After First Loop

```
Print 1

i++

i → 2
```

After Second Loop

```
Print 2

i++

i → 3
```

After Third Loop

```
Print 3

i++

i → 4
```

The loop continues until the condition becomes false.

---

# Difference Between `while` and `do...while`

## while Loop

```javascript
let i = 10;

while (i < 5) {
    console.log(i);
}
```

Output

```
Nothing
```

Because the condition is checked first.

---

## do...while Loop

```javascript
let i = 10;

do {
    console.log(i);
} while (i < 5);
```

Output

```
10
```

Because the code runs first.

---

# Comparison Table

| Feature | while | do...while |
|---------|--------|------------|
| Condition Checked | Before execution | After execution |
| Runs at least once | ❌ No | ✅ Yes |
| Best for | Normal loops | Menus, Login, Input |

---

# Real-Life Uses

## ATM Menu

```javascript
do {
    console.log("Choose an option");
} while (userWantsToContinue);
```

---

## Login System

```javascript
do {
    console.log("Enter Password");
} while (!correctPassword);
```

---

## Game Menu

```javascript
do {
    console.log("Play Game");
} while (playAgain);
```

---

## User Input Validation

```javascript
let age;

do {
    age = Number(prompt("Enter your age"));
} while (age <= 0);

console.log(age);
```

The program keeps asking until the user enters a valid age.

---

# Infinite Loop

```javascript
do {
    console.log("Hello");
} while (true);
```

Output

```
Hello
Hello
Hello
...
```

This loop never stops because the condition is always `true`.

---

# Common Mistakes

## 1. Forgetting the Semicolon

❌ Wrong

```javascript
do {
    console.log("Hello");
} while (false)
```

✅ Correct

```javascript
do {
    console.log("Hello");
} while (false);
```

---

## 2. Forgetting to Update the Variable

❌ Wrong

```javascript
let i = 1;

do {
    console.log(i);
} while (i <= 5);
```

The loop never ends because `i` never changes.

---

✅ Correct

```javascript
let i = 1;

do {
    console.log(i);
    i++;
} while (i <= 5);
```

---

## 3. Wrong Condition

❌ Wrong

```javascript
let i = 1;

do {
    console.log(i);
    i++;
} while (i >= 5);
```

Output

```
1
```

The condition becomes false after the first execution.

---

# Advantages

- Easy to understand.
- Executes at least one time.
- Useful for menus.
- Useful for login systems.
- Useful for user input validation.
- Good for retry operations.

---

# Disadvantages

- Runs once even if the condition is false.
- Can create an infinite loop if the variable is not updated.
- Not suitable when the condition must be checked before execution.

---

# Interview Questions

### 1. What is a `do...while` loop?

A `do...while` loop executes the code first and checks the condition afterward.

---

### 2. What is the main difference between `while` and `do...while`?

`while` checks the condition before execution.

`do...while` checks the condition after execution.

---

### 3. Will `do...while` execute if the condition is false?

Yes. It always executes at least one time.

---

### 4. Why do we use `do...while`?

When the code must run at least once, such as menus, login attempts, or user input.

---

### 5. Is the semicolon (`;`) required after `while(condition)`?

Yes.

```javascript
do {
    // code
} while (condition);
```

---

# Quick Revision

- `do...while` executes the code first.
- The condition is checked after execution.
- It always runs at least one time.
- Best for login systems, menus, games, and user input.
- Always update the loop variable.
- End the loop with a semicolon (`;`).

---

# Practice Programs

### Program 1

Print numbers from 1 to 10.

---

### Program 2

Print even numbers from 2 to 20.

---

### Program 3

Print odd numbers from 1 to 19.

---

### Program 4

Print the multiplication table of 7.

---

### Program 5

Find the sum of numbers from 1 to 100.

---

### Program 6

Print numbers in reverse from 20 to 1.

---

### Program 7

Keep asking the user for a positive number until a valid number is entered.

---

### Program 8

Create a simple menu that keeps displaying until the user chooses "Exit".