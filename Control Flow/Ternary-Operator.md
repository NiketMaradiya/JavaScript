# JavaScript Ternary Operator (`? :`)

The **Ternary Operator** is a **shortcut (short form)** of the `if...else` statement.

It checks a condition and returns **one value if the condition is true** and **another value if the condition is false**.

It is called the **Ternary Operator** because it works with **three parts**:

1. Condition
2. Value if condition is true
3. Value if condition is false

---

# Syntax

```javascript
condition ? valueIfTrue : valueIfFalse;
```

General Form

```
condition
    ?
 valueIfTrue
    :
valueIfFalse
```

---

# How It Works

```javascript
let age = 20;

let result = age >= 18 ? "Adult" : "Minor";

console.log(result);
```

Output

```
Adult
```

Explanation

```
age = 20

↓

age >= 18

↓

True

↓

Return "Adult"
```

---

# Compare with if...else

Using if...else

```javascript
let age = 20;
let result;

if (age >= 18) {
    result = "Adult";
} else {
    result = "Minor";
}

console.log(result);
```

Using Ternary Operator

```javascript
let age = 20;

let result = age >= 18 ? "Adult" : "Minor";

console.log(result);
```

Both produce the same output.

```
Adult
```

The ternary operator simply uses fewer lines of code.

---

# Example 1 : Even or Odd

```javascript
let number = 8;

let result = number % 2 === 0 ? "Even" : "Odd";

console.log(result);
```

Output

```
Even
```

---

# Example 2 : Pass or Fail

```javascript
let marks = 30;

let result = marks >= 35 ? "Pass" : "Fail";

console.log(result);
```

Output

```
Fail
```

---

# Example 3 : Login Status

```javascript
let isLoggedIn = true;

let message = isLoggedIn ? "Welcome" : "Please Login";

console.log(message);
```

Output

```
Welcome
```

---

# Example 4 : Stock Available

```javascript
let stock = 0;

let status = stock > 0 ? "Available" : "Out of Stock";

console.log(status);
```

Output

```
Out of Stock
```

---

# Example 5 : Driving License

```javascript
let age = 17;

let result = age >= 18 ? "Can Drive" : "Cannot Drive";

console.log(result);
```

Output

```
Cannot Drive
```

---

# Example 6 : Positive or Negative

```javascript
let num = -10;

let result = num >= 0 ? "Positive" : "Negative";

console.log(result);
```

Output

```
Negative
```

---

# Example 7 : Discount

```javascript
let amount = 1200;

let discount = amount >= 1000 ? "10% Discount" : "No Discount";

console.log(discount);
```

Output

```
10% Discount
```

---

# Example 8 : Free Shipping

```javascript
let total = 650;

let shipping = total >= 500 ? "Free Shipping" : "Shipping Charges";

console.log(shipping);
```

Output

```
Free Shipping
```

---

# Example 9 : Greeting

```javascript
let hour = 9;

let greeting = hour < 12 ? "Good Morning" : "Good Evening";

console.log(greeting);
```

Output

```
Good Morning
```

---

# Example 10 : Theme

```javascript
let darkMode = false;

let theme = darkMode ? "Dark Theme" : "Light Theme";

console.log(theme);
```

Output

```
Light Theme
```

---

# Assign Value Using Ternary

```javascript
let salary = 60000;

let level = salary > 50000 ? "High Salary" : "Normal Salary";

console.log(level);
```

Output

```
High Salary
```

---

# Ternary Inside console.log()

```javascript
let age = 15;

console.log(age >= 18 ? "Adult" : "Minor");
```

Output

```
Minor
```

---

# Nested Ternary Operator

Sometimes you need more than one condition.

```javascript
let marks = 82;

let grade =
    marks >= 90 ? "A" :
    marks >= 75 ? "B" :
    marks >= 60 ? "C" :
    "Fail";

console.log(grade);
```

Output

```
B
```

Flow

```
marks = 82

↓

82 >= 90 ?

No

↓

82 >= 75 ?

Yes

↓

Return "B"
```

---

# Real World Example 1

Shopping Website

```javascript
let isMember = true;
let price = 1000;

let finalPrice = isMember ? price - 100 : price;

console.log(finalPrice);
```

Output

```
900
```

---

# Real World Example 2

Login Button

```javascript
let loggedIn = false;

let button = loggedIn ? "Logout" : "Login";

console.log(button);
```

Output

```
Login
```

---

# Real World Example 3

Shopping Cart

```javascript
let cartItems = 3;

let message = cartItems > 0
    ? "Proceed to Checkout"
    : "Cart is Empty";

console.log(message);
```

Output

```
Proceed to Checkout
```

---

# Real World Example 4

Online Exam

```javascript
let marks = 91;

let result = marks >= 35 ? "Pass" : "Fail";

console.log(result);
```

Output

```
Pass
```

---

# Advantages

- Less code than `if...else`
- Easy to read for simple conditions
- Can directly assign values
- Commonly used in React
- Makes code cleaner

---

# Disadvantages

- Hard to read when nested many times
- Not good for complex business logic
- Can reduce readability if overused

---

# if...else vs Ternary Operator

| if...else | Ternary Operator |
|-----------|------------------|
| Long syntax | Short syntax |
| Better for complex logic | Best for simple conditions |
| More readable | Less code |
| Can execute many statements | Returns one value |

---

# Common Mistakes

## Mistake 1

```javascript
let age = 20;

age >= 18 ? "Adult";
```

❌ Wrong

Reason:

The ternary operator always needs both the **true** and **false** values.

Correct

```javascript
let age = 20;

age >= 18 ? "Adult" : "Minor";
```

---

## Mistake 2

```javascript
let age = 18;

let result = age = 18 ? "Adult" : "Minor";
```

❌ Wrong

Reason:

`=` means assignment.

Correct

```javascript
let result = age >= 18 ? "Adult" : "Minor";
```

---

# Best Practices

✔ Use the ternary operator for simple conditions.

✔ Use `if...else` for complex logic.

✔ Keep nested ternary operators to a minimum.

✔ Write readable code.

---

# Interview Questions

## 1. What is the Ternary Operator?

The Ternary Operator is the short form of the `if...else` statement.

---

## 2. What is its syntax?

```javascript
condition ? valueIfTrue : valueIfFalse;
```

---

## 3. Why is it called the Ternary Operator?

Because it uses **three operands**:

- Condition
- True value
- False value

---

## 4. Can we replace every if...else with a ternary operator?

No.

Use a ternary operator only for simple conditions.

---

## 5. Can we nest ternary operators?

Yes.

Example

```javascript
let marks = 85;

let grade =
marks >= 90 ? "A" :
marks >= 75 ? "B" :
marks >= 60 ? "C" :
"Fail";

console.log(grade);
```

---

## 6. Does the ternary operator return a value?

Yes.

It always returns either the **true value** or the **false value**.

---

## 7. Where is the ternary operator commonly used?

- React JSX
- Node.js
- Conditional rendering
- Variable assignment
- UI messages
- Buttons
- Validation

---

# Quick Revision

```
Ternary Operator

Syntax

condition ? trueValue : falseValue;

Purpose

✔ Replace simple if...else
✔ Return one value
✔ Write shorter code

Example

let age = 20;

let result = age >= 18
    ? "Adult"
    : "Minor";

Output

Adult

Best For

✔ Simple conditions

Avoid

❌ Complex nested logic
```