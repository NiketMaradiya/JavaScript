# JavaScript Variables (var, let, const)

# What is a Variable?

Imagine you have a school bag.

Inside the bag you can keep:

📚 Books
✏️ Pens
📱 Mobile
💰 Money

A variable is exactly like that bag.

Instead of storing books, JavaScript variables store data.

Example:

```javascript
let age = 20;
```

Memory:

```
+----------------+
| Variable Name  |
| age            |
+----------------+
| Value          |
| 20             |
+----------------+
```

JavaScript remembers:

```
age → 20
```

Now print it.

```javascript
let age = 20;

console.log(age);
```

Output:

```
20
```

---

# Change the Value

```javascript
let age = 20;

age = 21;

console.log(age);
```

Memory Before

```
age → 20
```

Memory After

```
age → 21
```

Output

```
21
```

Question:

Why did the value change?

Answer:

Because we used **let**.

`let` allows us to change the value.

---

# Real-Life Example

Imagine your wallet.

Morning:

```
Wallet = ₹1000
```

You buy a pizza.

```
Wallet = ₹700
```

You receive salary.

```
Wallet = ₹5700
```

JavaScript:

```javascript
let wallet = 1000;

wallet = wallet - 300;

wallet = wallet + 5000;

console.log(wallet);
```

Output

```
5700
```

This is why we use `let`.

The value changes.

---

# Think Like a Programmer

When you see this:

```javascript
let score = 0;
```

Don't read it as code.

Read it like this:

> "Create a box named `score` and put the value `0` inside it."

Memory:

```
+---------+
| score   |
+---------+
|   0     |
+---------+
```

Then:

```javascript
score = score + 10;
```

Memory:

```
+---------+
| score   |
+---------+
|   10    |
+---------+
```

Then:

```javascript
score = score + 20;
```

Memory:

```
+---------+
| score   |
+---------+
|   30    |
+---------+
```

Output

```
30
```

---

# Mini Project

Game Score

```javascript
const playerName = "Niket";

let score = 0;

score += 100;
score += 50;
score -= 20;

console.log(playerName);
console.log(score);
```

Output

```
Niket
130
```

Programmer Thinking:

```
Player joins game

↓

Score starts at 0

↓

Wins battle

↓

+100

↓

Collects coin

↓

+50

↓

Hits obstacle

↓

-20

↓

Final Score = 130
```

---

# Common Mistake

Wrong

```javascript
const age = 20;

age = 21;
```

Error

```
TypeError
```

Why?

Because `const` means:

> "Do not assign a new value."

Correct

```javascript
let age = 20;

age = 21;
```

---

# Interview Question

Q. When should you use `let`?

Answer:

When the value changes.

Examples:

✅ Score

✅ Bank Balance

✅ Cart Quantity

✅ Login Status

✅ Counter

---

# Practice

Write a program for:

1. ATM Balance
2. Cricket Score
3. Shopping Cart
4. Student Marks
5. Mobile Battery Percentage

Try changing the value after every step.