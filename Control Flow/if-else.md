# JavaScript `if / else` (Complete Guide)

## What is `if / else`?

`if / else` is a **decision-making statement** in JavaScript.

It checks whether a condition is **true** or **false**.

- If the condition is **true**, the `if` block runs.
- If the condition is **false**, the `else` block runs.

### Real Life Example

Imagine you are going outside.

```
If it is raining
    Take an umbrella
Else
    Wear sunglasses
```

JavaScript works in the same way.

---

# Syntax

```javascript
if (condition) {
    // Code runs if condition is true
} else {
    // Code runs if condition is false
}
```

---

# Flow Chart

```
            Start
              │
              ▼
      Is condition true?
         /           \
      Yes             No
      │               │
      ▼               ▼
 Run if block    Run else block
      │               │
      └───────┬───────┘
              ▼
             End
```

---

# Example 1 : Check Age

```javascript
let age = 20;

if (age >= 18) {
    console.log("You can vote");
} else {
    console.log("You cannot vote");
}
```

### Output

```
You can vote
```

### How JavaScript Executes

```
age = 20

↓

20 >= 18

↓

True

↓

Run if block

↓

Print "You can vote"
```

---

# Example 2 : Age Less Than 18

```javascript
let age = 15;

if (age >= 18) {
    console.log("You can vote");
} else {
    console.log("You cannot vote");
}
```

### Output

```
You cannot vote
```

---

# Example 3 : Positive or Negative Number

```javascript
let number = -5;

if (number >= 0) {
    console.log("Positive Number");
} else {
    console.log("Negative Number");
}
```

### Output

```
Negative Number
```

---

# Example 4 : Pass or Fail

```javascript
let marks = 70;

if (marks >= 35) {
    console.log("Pass");
} else {
    console.log("Fail");
}
```

### Output

```
Pass
```

---

# Example 5 : Even or Odd Number

```javascript
let number = 8;

if (number % 2 === 0) {
    console.log("Even Number");
} else {
    console.log("Odd Number");
}
```

### Output

```
Even Number
```

---

# Comparison Operators with if

## Greater Than (>)

```javascript
let age = 25;

if (age > 18) {
    console.log("Adult");
}
```

Output

```
Adult
```

---

## Less Than (<)

```javascript
let age = 10;

if (age < 18) {
    console.log("Child");
}
```

Output

```
Child
```

---

## Equal (==)

```javascript
let a = 10;

if (a == "10") {
    console.log("Equal");
}
```

Output

```
Equal
```

**Reason**

`==` compares only values after type conversion.

---

## Strict Equal (===)

```javascript
let a = 10;

if (a === "10") {
    console.log("Equal");
} else {
    console.log("Not Equal");
}
```

Output

```
Not Equal
```

**Reason**

```
10 → Number
"10" → String
```

Different data types.

---

# Logical AND (&&)

Both conditions must be true.

```javascript
let age = 22;
let citizen = true;

if (age >= 18 && citizen) {
    console.log("Eligible to Vote");
} else {
    console.log("Not Eligible");
}
```

Output

```
Eligible to Vote
```

---

# Logical OR (||)

Only one condition needs to be true.

```javascript
let holiday = false;
let sunday = true;

if (holiday || sunday) {
    console.log("No Office");
}
```

Output

```
No Office
```

---

# Logical NOT (!)

```javascript
let isLoggedIn = false;

if (!isLoggedIn) {
    console.log("Please Login");
}
```

Output

```
Please Login
```

---

# Multiple Statements

```javascript
let salary = 50000;

if (salary > 30000) {
    console.log("Good Salary");
    console.log("Loan Approved");
    console.log("Congratulations");
}
```

Output

```
Good Salary
Loan Approved
Congratulations
```

---

# Nested if

A Nested `if` means one `if` statement inside another `if`.

```javascript
let age = 20;
let hasLicense = true;

if (age >= 18) {

    if (hasLicense) {
        console.log("You can drive");
    }

}
```

Output

```
You can drive
```

---

# else if

When multiple conditions need to be checked, use `else if`.

```javascript
let marks = 82;

if (marks >= 90) {
    console.log("Grade A");
}
else if (marks >= 75) {
    console.log("Grade B");
}
else if (marks >= 50) {
    console.log("Grade C");
}
else {
    console.log("Fail");
}
```

Output

```
Grade B
```

Execution

```
marks = 82

↓

82 >= 90

False

↓

82 >= 75

True

↓

Grade B

↓

Program Stops
```

---

# Real World Examples

## 1. ATM Machine

```javascript
let balance = 5000;
let withdraw = 3000;

if (withdraw <= balance) {
    console.log("Transaction Successful");
} else {
    console.log("Insufficient Balance");
}
```

Output

```
Transaction Successful
```

---

## 2. Login System

```javascript
let password = "admin123";

if (password === "admin123") {
    console.log("Login Successful");
} else {
    console.log("Wrong Password");
}
```

Output

```
Login Successful
```

---

## 3. Shopping Discount

```javascript
let amount = 7000;

if (amount >= 5000) {
    console.log("20% Discount");
} else {
    console.log("No Discount");
}
```

Output

```
20% Discount
```

---

## 4. Traffic Signal

```javascript
let signal = "Red";

if (signal === "Green") {
    console.log("Go");
} else {
    console.log("Stop");
}
```

Output

```
Stop
```

---

## 5. Student Result

```javascript
let marks = 95;

if (marks >= 90) {
    console.log("Excellent");
} else {
    console.log("Keep Practicing");
}
```

Output

```
Excellent
```

---

# Common Mistakes

## ❌ Using = Instead of == or ===

Wrong

```javascript
let age = 18;

if (age = 20) {
    console.log("Adult");
}
```

`=` assigns a value instead of comparing it.

Correct

```javascript
if (age === 20) {
    console.log("Adult");
}
```

---

## ❌ Forgetting Curly Braces

Wrong

```javascript
if (age >= 18)
    console.log("Adult");
    console.log("Welcome");
```

Output

```
Adult
Welcome
```

`Welcome` always runs because it is outside the `if` block.

Correct

```javascript
if (age >= 18) {
    console.log("Adult");
    console.log("Welcome");
}
```

---

## ❌ Comparing Different Data Types

```javascript
let age = "18";

if (age === 18) {
    console.log("Adult");
}
```

Nothing is printed because:

```
"18" → String
18 → Number
```

---

# Best Practices

✅ Always use `===`

✅ Always use curly braces `{}`

✅ Keep conditions simple

✅ Use meaningful variable names

✅ Use `else if` when checking multiple conditions

---

# Interview Questions

### 1. What is `if` in JavaScript?

**Answer:** `if` is a conditional statement used to execute code only when a condition is true.

---

### 2. What is the difference between `if` and `if...else`?

**Answer:**

- `if` runs code only when the condition is true.
- `if...else` runs one block if true and another block if false.

---

### 3. What is `else if`?

**Answer:** `else if` is used to check multiple conditions one after another.

---

### 4. What is the difference between `==` and `===`?

**Answer:**

- `==` compares only values after type conversion.
- `===` compares both value and data type.

---

### 5. What happens if the condition is false and there is no `else`?

**Answer:** The `if` block is skipped, and the program continues with the next statement.

---

### 6. What is a Nested `if`?

**Answer:** A Nested `if` is an `if` statement inside another `if` statement.

---

### 7. Can we write an `if` statement without braces?

**Answer:** Yes, but only for one statement. Using braces `{}` is recommended.

---

### 8. Which values are considered false in an `if` condition?

**Answer:**

- false
- 0
- ""
- null
- undefined
- NaN
- 0n

---

# Quick Summary

- `if` checks a condition.
- `else` runs when the condition is false.
- `else if` checks multiple conditions.
- Use `===` instead of `==`.
- Use `{}` for better readability.
- `if / else` is used in login systems, ATM machines, shopping carts, form validation, access control, and many real-world applications.