# JavaScript While Loop

## What is a While Loop?

A **while loop** is used to execute a block of code **repeatedly** as long as a **condition is true**.

It first checks the condition.

- If the condition is **true**, the code runs.
- If the condition is **false**, the loop stops.

---

# Syntax

```javascript
while (condition) {
    // Code to execute
}
```

---

# Flow of While Loop

```

Start
│
▼
Check Condition
│
├── True ──► Run Code
│             │
│             ▼
│         Update Variable
│             │
└─────────────┘

False
│
▼
End

```

---

# Real-Life Example

Imagine you are drinking water.

Rule:

**While the bottle has water, keep drinking.**

```

Bottle has water? → Yes

↓

Drink Water

↓

Bottle has water? → Yes

↓

Drink Water

↓

Bottle has water? → No

↓

Stop Drinking

```

This is exactly how a **while loop** works.

---

# Example 1: Print Numbers 1 to 5

```javascript
let i = 1;

while (i <= 5) {
    console.log(i);
    i++;
}
```

## Output

```
1
2
3
4
5
```

---

# Step-by-Step Execution

### Before Loop

```
i = 1
```

### Iteration 1

```
Condition

1 <= 5

True

Print 1

i becomes 2
```

### Iteration 2

```
Condition

2 <= 5

True

Print 2

i becomes 3
```

### Iteration 3

```
Condition

3 <= 5

True

Print 3

i becomes 4
```

### Iteration 4

```
Condition

4 <= 5

True

Print 4

i becomes 5
```

### Iteration 5

```
Condition

5 <= 5

True

Print 5

i becomes 6
```

### Final Check

```
Condition

6 <= 5

False

Loop Stops
```

---

# Memory Representation

Before Loop

```
i → 1
```

After First Iteration

```
i → 2
```

After Second Iteration

```
i → 3
```

After Third Iteration

```
i → 4
```

After Fourth Iteration

```
i → 5
```

After Fifth Iteration

```
i → 6

Condition False

Stop
```

---

# Example 2: Print Even Numbers

```javascript
let num = 2;

while (num <= 10) {
    console.log(num);
    num += 2;
}
```

## Output

```
2
4
6
8
10
```

---

# Example 3: Countdown

```javascript
let count = 5;

while (count >= 1) {
    console.log(count);
    count--;
}

console.log("Blast Off!");
```

## Output

```
5
4
3
2
1
Blast Off!
```

---

# Example 4: Multiplication Table

```javascript
let i = 1;

while (i <= 10) {
    console.log(`7 x ${i} = ${7 * i}`);
    i++;
}
```

## Output

```
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```

---

# Example 5: Sum of Numbers

```javascript
let i = 1;
let sum = 0;

while (i <= 5) {
    sum = sum + i;
    i++;
}

console.log(sum);
```

## Output

```
15
```

### Calculation

```
0 + 1 = 1

1 + 2 = 3

3 + 3 = 6

6 + 4 = 10

10 + 5 = 15
```

---

# Example 6: Print Array Elements

```javascript
let fruits = ["Apple", "Banana", "Mango", "Orange"];

let index = 0;

while (index < fruits.length) {
    console.log(fruits[index]);
    index++;
}
```

## Output

```
Apple
Banana
Mango
Orange
```

---

# Example 7: Reverse Counting

```javascript
let i = 10;

while (i >= 1) {
    console.log(i);
    i--;
}
```

## Output

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

# Example 8: Login Attempts

```javascript
let attempts = 1;

while (attempts <= 3) {
    console.log("Wrong Password");
    attempts++;
}

console.log("Account Locked");
```

## Output

```
Wrong Password
Wrong Password
Wrong Password
Account Locked
```

---

# Example 9: Infinite Loop

```javascript
let i = 1;

while (i <= 5) {
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
1
1
...
```

Why?

Because **i never changes**.

The condition always remains **true**.

This is called an **Infinite Loop**.

---

# Correct Version

```javascript
let i = 1;

while (i <= 5) {
    console.log(i);
    i++;
}
```

---

# While Loop Flow Diagram

```

i = 1

↓

Check Condition

↓

True

↓

Run Code

↓

Increase i

↓

Go Back

↓

Condition Again

↓

False

↓

End

```

---

# While vs For Loop

| Feature | while | for |
|---------|-------|-----|
| Condition checked first | ✅ Yes | ✅ Yes |
| Initialization | Outside Loop | Inside Loop |
| Increment | Inside Loop | Inside for() |
| Best for Unknown Iterations | ✅ Yes | ❌ No |
| Best for Counting | ✅ Good | ✅ Best |

---

# Common Mistakes

## 1. Forgetting i++

```javascript
let i = 1;

while (i <= 5) {
    console.log(i);
}
```

❌ Infinite Loop

---

## 2. Wrong Condition

```javascript
let i = 10;

while (i <= 5) {
    console.log(i);
}
```

Output

```
Nothing
```

Because

```
10 <= 5

False
```

---

## 3. Wrong Direction

```javascript
let i = 5;

while (i >= 1) {
    console.log(i);
    i++;
}
```

Output

```
5
6
7
8
9
...
```

❌ Infinite Loop

---

# When to Use While Loop?

Use **while** when:

- Number of iterations is unknown.
- Waiting for user input.
- Reading data until the end.
- Login attempts.
- Game loops.
- Download progress.
- Network requests.
- Menu-driven programs.

---

# Advantages

- Easy to understand.
- Good for unknown iterations.
- Flexible.
- Less code for condition-based loops.

---

# Disadvantages

- Can easily create infinite loops.
- Need to manually update the variable.
- Less readable for fixed iterations compared to `for`.

---

# Interview Questions

## 1. What is a while loop?

A while loop executes a block of code repeatedly **while the condition is true**.

---

## 2. When is the condition checked?

Before every iteration.

---

## 3. Can a while loop run zero times?

Yes.

Example

```javascript
let i = 10;

while (i < 5) {
    console.log(i);
}
```

Output

```
No Output
```

---

## 4. What is an Infinite Loop?

A loop that never stops because its condition never becomes false.

Example

```javascript
while (true) {
    console.log("Hello");
}
```

---

## 5. Difference Between while and do...while?

| while | do...while |
|--------|------------|
| Checks condition first | Runs once, then checks condition |
| May execute 0 times | Executes at least 1 time |

---

# Summary

- `while` repeats code **while the condition is true**.
- Condition is checked **before** each iteration.
- Always update the loop variable (`i++`, `i--`) to avoid infinite loops.
- Use `while` when the number of iterations is **not known in advance**.
- It is commonly used for login attempts, reading files, games, and condition-based tasks.