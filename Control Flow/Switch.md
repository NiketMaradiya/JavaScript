# JavaScript Switch Statement

A complete beginner-friendly guide with examples.

---

# What is `switch`?

The `switch` statement is used to compare **one value** with **multiple possible values**.

Instead of writing many `if...else if...else` statements, we can use `switch` to make the code cleaner and easier to read.

---

# Real Life Example

Imagine you are ordering food in a restaurant.

The waiter asks:

Which food do you want?

- Pizza
- Burger
- Sandwich
- Pasta

Depending on your choice, the waiter serves your food.

JavaScript `switch` works in the same way.

```
           User Choice
                │
                ▼
        +----------------+
        | switch(choice) |
        +----------------+
          │   │   │   │
          │   │   │   │
       Pizza Burger Pasta Sandwich
          │      │      │      │
          ▼      ▼      ▼      ▼
     Serve Pizza Burger Pasta Sandwich
```

---

# Syntax

```javascript
switch (expression) {

    case value1:
        // Code
        break;

    case value2:
        // Code
        break;

    case value3:
        // Code
        break;

    default:
        // Code
}
```

---

# How switch Works

Step 1

JavaScript reads the value inside `switch()`.

```javascript
let day = 2;

switch(day)
```

Step 2

It compares the value with every case.

```
day = 2

case 1 ❌

case 2 ✅

case 3 ❌
```

Step 3

When a matching case is found, that block runs.

Step 4

If there is a `break`, JavaScript exits the switch.

---

# Example 1

```javascript
let day = 1;

switch(day){

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
        console.log("Invalid Day");
}
```

Output

```
Monday
```

---

# Example 2

```javascript
let day = 3;

switch(day){

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

Output

```
Wednesday
```

---

# Example 3 (String)

```javascript
let fruit = "Apple";

switch(fruit){

    case "Banana":
        console.log("Yellow Fruit");
        break;

    case "Apple":
        console.log("Red Fruit");
        break;

    case "Orange":
        console.log("Orange Fruit");
        break;

    default:
        console.log("Unknown Fruit");
}
```

Output

```
Red Fruit
```

---

# Example 4 (Student Grade)

```javascript
let grade = "A";

switch(grade){

    case "A":
        console.log("Excellent");
        break;

    case "B":
        console.log("Good");
        break;

    case "C":
        console.log("Average");
        break;

    default:
        console.log("Fail");
}
```

Output

```
Excellent
```

---

# What is `break`?

`break` tells JavaScript:

> Stop executing the switch statement.

Without `break`, JavaScript continues running the next cases.

---

# Example Without break

```javascript
let day = 2;

switch(day){

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

Output

```
Tuesday
Wednesday
Invalid
```

Because there is no `break`.

Execution continues until the switch ends.

This is called **Fall Through**.

---

# Example With break

```javascript
let day = 2;

switch(day){

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

Output

```
Tuesday
```

---

# What is `default`?

`default` works like the `else` block.

It runs only when no case matches.

Example

```javascript
let color = "Pink";

switch(color){

    case "Red":
        console.log("Stop");
        break;

    case "Green":
        console.log("Go");
        break;

    default:
        console.log("Color Not Found");
}
```

Output

```
Color Not Found
```

---

# Multiple Cases Together

Sometimes different values should execute the same code.

```javascript
let day = 6;

switch(day){

    case 6:
    case 7:
        console.log("Weekend");
        break;

    default:
        console.log("Weekday");
}
```

Output

```
Weekend
```

---

# Calculator Example

```javascript
let num1 = 20;
let num2 = 10;
let operator = "+";

switch(operator){

    case "+":
        console.log(num1 + num2);
        break;

    case "-":
        console.log(num1 - num2);
        break;

    case "*":
        console.log(num1 * num2);
        break;

    case "/":
        console.log(num1 / num2);
        break;

    default:
        console.log("Invalid Operator");
}
```

Output

```
30
```

---

# Switch vs If Else

## Using if...else

```javascript
let day = 2;

if(day === 1){
    console.log("Monday");
}
else if(day === 2){
    console.log("Tuesday");
}
else if(day === 3){
    console.log("Wednesday");
}
else{
    console.log("Invalid Day");
}
```

---

## Using switch

```javascript
let day = 2;

switch(day){

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
        console.log("Invalid Day");
}
```

Both give the same result.

`switch` is cleaner when checking one variable against many fixed values.

---

# When to Use switch

Use switch when:

- Menu systems
- User roles
- Days
- Months
- Calculator
- Game levels
- Language selection

---

# When NOT to Use switch

Do not use switch for range checking.

Example

```javascript
if(age >= 18){
    console.log("Adult");
}
```

This is better than switch.

---

# Common Mistakes

## 1. Forgetting break

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

## 2. Forgetting default

```javascript
switch(day){

    case 1:
        console.log("Monday");
        break;
}
```

If no case matches, nothing happens.

---

## 3. Case Sensitive Values

```javascript
let fruit = "apple";

switch(fruit){

    case "Apple":
        console.log("Found");
}
```

Output

```
Nothing
```

Because

```
apple != Apple
```

---

# Memory Flow

```
day = 2

        │
        ▼

switch(day)

        │

case 1 ❌

case 2 ✅

Print "Tuesday"

break

Exit
```

---

# Interview Questions

### 1. What is switch in JavaScript?

A switch statement compares one expression with multiple values and executes the matching case.

---

### 2. Why do we use break?

To stop the execution after a matching case.

---

### 3. What happens if break is missing?

JavaScript executes all remaining cases after the matched case. This is called **Fall Through**.

---

### 4. What is default?

It executes when no case matches.

---

### 5. Can switch use strings?

Yes.

```javascript
switch(role){

    case "admin":
        console.log("Admin");

}
```

---

### 6. Can multiple cases share one block?

Yes.

```javascript
switch(day){

    case 6:
    case 7:
        console.log("Weekend");
        break;
}
```

---

### 7. Can switch check ranges like age > 18?

No.

For ranges and complex conditions, use `if...else`.

---

# Quick Revision

| Keyword | Purpose |
|----------|---------|
| switch | Compare one value with many values |
| case | Matching value |
| break | Exit switch |
| default | Runs when no case matches |
| Fall Through | Happens when break is missing |
| Best Use | Menus, Days, Months, Roles, Calculator |

---

# Short Notes

- `switch` compares one value.
- Every `case` is checked one by one.
- The matching case is executed.
- `break` stops execution.
- `default` works like `else`.
- Missing `break` causes Fall Through.
- `switch` is cleaner than many `if...else if` statements when checking one variable.