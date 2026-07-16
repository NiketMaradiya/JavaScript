# Default Parameters in JavaScript

Default Parameters allow us to give a default value to a function parameter.

When a function is called without an argument, JavaScript automatically uses the default value.

Default Parameters were introduced in **ES6 (ECMAScript 2015)**.

---

## Syntax

```javascript
function functionName(parameter = defaultValue) {
  // Function code
}
```

Example:

```javascript
function greet(name = "Guest") {
  console.log("Hello " + name);
}

greet();
```

Output:

```text
Hello Guest
```

In this example:

* `name` is the parameter.
* `"Guest"` is the default value.
* Because no argument is passed, JavaScript uses `"Guest"`.

---

## Basic Example

```javascript
function greet(name = "Guest") {
  console.log("Hello " + name);
}

greet();
greet("Niket");
```

Output:

```text
Hello Guest
Hello Niket
```

Explanation:

```text
greet()
```

No value is passed, so:

```text
name = "Guest"
```

In the second function call:

```text
greet("Niket")
```

A value is passed, so:

```text
name = "Niket"
```

The passed value replaces the default value.

---

## Why Do We Need Default Parameters?

Suppose we create this function:

```javascript
function greet(name) {
  console.log("Hello " + name);
}

greet();
```

Output:

```text
Hello undefined
```

Because no argument was passed, the value of `name` became `undefined`.

We can solve this problem with a Default Parameter:

```javascript
function greet(name = "Guest") {
  console.log("Hello " + name);
}

greet();
```

Output:

```text
Hello Guest
```

---

## Old Method Before ES6

Before Default Parameters, developers used conditions or the logical OR operator.

```javascript
function greet(name) {
  name = name || "Guest";

  console.log("Hello " + name);
}

greet();
```

Output:

```text
Hello Guest
```

However, this method has a problem.

```javascript
function showNumber(number) {
  number = number || 10;

  console.log(number);
}

showNumber(0);
```

Output:

```text
10
```

We passed `0`, but JavaScript used `10`.

This happens because `0` is a falsy value.

Default Parameters solve this problem:

```javascript
function showNumber(number = 10) {
  console.log(number);
}

showNumber(0);
```

Output:

```text
0
```

---

## Default Parameter with Numbers

```javascript
function square(number = 5) {
  console.log(number * number);
}

square();
square(4);
```

Output:

```text
25
16
```

Explanation:

```text
square()

number = 5
5 × 5 = 25
```

```text
square(4)

number = 4
4 × 4 = 16
```

---

## Default Parameter with Strings

```javascript
function showCountry(country = "India") {
  console.log(country);
}

showCountry();
showCountry("Canada");
```

Output:

```text
India
Canada
```

---

## Default Parameter with Boolean Values

```javascript
function checkAdmin(isAdmin = false) {
  console.log(isAdmin);
}

checkAdmin();
checkAdmin(true);
```

Output:

```text
false
true
```

---

## Multiple Default Parameters

A function can have more than one Default Parameter.

```javascript
function add(a = 10, b = 20) {
  console.log(a + b);
}

add();
add(5);
add(5, 10);
```

Output:

```text
30
25
15
```

Explanation:

### First Function Call

```javascript
add();
```

JavaScript uses both default values:

```text
a = 10
b = 20

10 + 20 = 30
```

### Second Function Call

```javascript
add(5);
```

The value of `a` is replaced, but `b` uses its default value:

```text
a = 5
b = 20

5 + 20 = 25
```

### Third Function Call

```javascript
add(5, 10);
```

Both values are provided:

```text
a = 5
b = 10

5 + 10 = 15
```

---

## Default Parameter with an Array

```javascript
function showSkills(skills = []) {
  console.log(skills);
}

showSkills();

showSkills([
  "HTML",
  "CSS",
  "JavaScript"
]);
```

Output:

```text
[]
["HTML", "CSS", "JavaScript"]
```

We can also loop through the array:

```javascript
function showSkills(skills = []) {
  for (const skill of skills) {
    console.log(skill);
  }
}

showSkills([
  "HTML",
  "CSS",
  "JavaScript"
]);
```

Output:

```text
HTML
CSS
JavaScript
```

---

## Default Parameter with an Object

```javascript
function showUser(user = {
  name: "Unknown",
  age: 0
}) {
  console.log(user);
}

showUser();

showUser({
  name: "Niket",
  age: 21
});
```

Output:

```text
{ name: "Unknown", age: 0 }
{ name: "Niket", age: 21 }
```

We can access the object properties:

```javascript
function showUser(user = {
  name: "Unknown",
  age: 0
}) {
  console.log("Name:", user.name);
  console.log("Age:", user.age);
}

showUser();
```

Output:

```text
Name: Unknown
Age: 0
```

---

## Passing `undefined`

When we pass `undefined`, JavaScript uses the default value.

```javascript
function greet(name = "Guest") {
  console.log(name);
}

greet(undefined);
```

Output:

```text
Guest
```

These two function calls behave in the same way:

```javascript
greet();
greet(undefined);
```

Both use the default value.

---

## Passing `null`

`null` does not activate the default value.

```javascript
function greet(name = "Guest") {
  console.log(name);
}

greet(null);
```

Output:

```text
null
```

This happens because `null` is considered an actual value.

Remember:

```text
undefined → Default value is used

null → Default value is not used
```

---

## Passing Zero

Zero is a valid value, so the default value is not used.

```javascript
function showPrice(price = 100) {
  console.log(price);
}

showPrice(0);
```

Output:

```text
0
```

---

## Passing `false`

`false` is also a valid value.

```javascript
function checkStatus(status = true) {
  console.log(status);
}

checkStatus(false);
```

Output:

```text
false
```

---

## Passing an Empty String

An empty string is a valid value.

```javascript
function greet(name = "Guest") {
  console.log("Hello " + name);
}

greet("");
```

Output:

```text
Hello
```

The default value is not used because an empty string was passed.

---

## Default Parameter Using Another Parameter

A Default Parameter can use a parameter declared before it.

```javascript
function calculatePrice(price, tax = price * 0.18) {
  console.log("Price:", price);
  console.log("Tax:", tax);
}

calculatePrice(1000);
```

Output:

```text
Price: 1000
Tax: 180
```

Here, the default value of `tax` is calculated using `price`.

Another example:

```javascript
function showName(firstName, lastName = firstName) {
  console.log(firstName + " " + lastName);
}

showName("Niket");
showName("Niket", "Maradiya");
```

Output:

```text
Niket Niket
Niket Maradiya
```

---

## Default Parameter with an Expression

A Default Parameter can contain an expression.

```javascript
function calculateTotal(
  price,
  quantity = 2,
  total = price * quantity
) {
  console.log(total);
}

calculateTotal(500);
```

Output:

```text
1000
```

Calculation:

```text
price = 500
quantity = 2
total = 500 × 2

total = 1000
```

---

## Default Parameter with a Function Call

A function can be called to generate the default value.

```javascript
function getDefaultPrice() {
  return 100;
}

function showPrice(price = getDefaultPrice()) {
  console.log(price);
}

showPrice();
showPrice(500);
```

Output:

```text
100
500
```

The `getDefaultPrice()` function runs only when the argument is missing or `undefined`.

---

## Default Value Is Evaluated When Needed

```javascript
let count = 0;

function generateValue() {
  count++;

  return count;
}

function showValue(value = generateValue()) {
  console.log(value);
}

showValue();
showValue();
showValue(100);
```

Output:

```text
1
2
100
```

Explanation:

* First call uses `generateValue()` and returns `1`.
* Second call uses `generateValue()` and returns `2`.
* Third call receives `100`, so `generateValue()` is not called.

---

## Default Parameters with Arrow Functions

Default Parameters also work with Arrow Functions.

```javascript
const multiply = (a = 2, b = 3) => {
  return a * b;
};

console.log(multiply());
console.log(multiply(5));
console.log(multiply(5, 10));
```

Output:

```text
6
15
50
```

A shorter version:

```javascript
const multiply = (a = 2, b = 3) => a * b;

console.log(multiply());
```

Output:

```text
6
```

---

## Default Parameters with Function Expressions

```javascript
const greet = function (name = "Guest") {
  console.log("Hello " + name);
};

greet();
greet("Niket");
```

Output:

```text
Hello Guest
Hello Niket
```

---

## Skipping the First Parameter

Suppose the first parameter also has a default value:

```javascript
function introduce(
  name = "Guest",
  age = 18
) {
  console.log(name, age);
}
```

To use the default value of `name` but provide an age, pass `undefined`.

```javascript
introduce(undefined, 25);
```

Output:

```text
Guest 25
```

Do not use `null`:

```javascript
introduce(null, 25);
```

Output:

```text
null 25
```

Because `null` does not activate the default value.

---

# Real-World Example: Product Order

```javascript
function placeOrder(
  product,
  quantity = 1,
  shippingCharge = 50
) {
  console.log("Product:", product);
  console.log("Quantity:", quantity);
  console.log("Shipping Charge:", shippingCharge);
}

placeOrder("Laptop");

placeOrder("Mouse", 2);

placeOrder("Mobile", 3, 100);
```

Output:

```text
Product: Laptop
Quantity: 1
Shipping Charge: 50

Product: Mouse
Quantity: 2
Shipping Charge: 50

Product: Mobile
Quantity: 3
Shipping Charge: 100
```

---

# Real-World Example: User Registration

```javascript
function registerUser(
  username,
  role = "user",
  isActive = true
) {
  console.log("Username:", username);
  console.log("Role:", role);
  console.log("Active:", isActive);
}

registerUser("Niket");
```

Output:

```text
Username: Niket
Role: user
Active: true
```

Admin example:

```javascript
registerUser("Admin", "admin", true);
```

Output:

```text
Username: Admin
Role: admin
Active: true
```

---

# Real-World Example: Calculate Product Total

```javascript
function calculateTotal(
  price,
  quantity = 1,
  discount = 0
) {
  const subtotal = price * quantity;

  const discountAmount =
    subtotal * discount / 100;

  const finalTotal =
    subtotal - discountAmount;

  console.log("Subtotal:", subtotal);
  console.log("Discount:", discountAmount);
  console.log("Final Total:", finalTotal);
}

calculateTotal(1000);
```

Output:

```text
Subtotal: 1000
Discount: 0
Final Total: 1000
```

With quantity and discount:

```javascript
calculateTotal(1000, 2, 10);
```

Output:

```text
Subtotal: 2000
Discount: 200
Final Total: 1800
```

---

# Common Errors and Mistakes

## Error 1: Using a Later Parameter

A parameter cannot use another parameter declared after it.

Incorrect code:

```javascript
function calculate(a = b, b = 10) {
  console.log(a, b);
}

calculate();
```

Error:

```text
ReferenceError: Cannot access 'b' before initialization
```

Reason:

`b` is declared after `a`, so it is not available when JavaScript calculates the default value of `a`.

Correct code:

```javascript
function calculate(a = 10, b = a) {
  console.log(a, b);
}

calculate();
```

Output:

```text
10 10
```

---

## Error 2: Expecting `null` to Use the Default Value

Incorrect expectation:

```javascript
function greet(name = "Guest") {
  console.log(name);
}

greet(null);
```

Output:

```text
null
```

Correct method:

```javascript
greet(undefined);
```

Output:

```text
Guest
```

---

## Error 3: Missing a Required Parameter

```javascript
function login(
  username,
  password = "1234"
) {
  console.log(username, password);
}

login();
```

Output:

```text
undefined 1234
```

Only `password` has a default value.

The `username` parameter does not have a default value, so it becomes `undefined`.

A safer version:

```javascript
function login(
  username = "Guest",
  password = "1234"
) {
  console.log(username, password);
}

login();
```

Output:

```text
Guest 1234
```

---

## Error 4: Using Default Parameters for Required Data

This code may hide an important error:

```javascript
function createUser(
  email = "unknown@example.com"
) {
  console.log(email);
}
```

An email may be required for creating a user.

A better method is to throw an error when the required value is missing.

```javascript
function requiredParameter(parameterName) {
  throw new Error(
    `${parameterName} is required`
  );
}

function createUser(
  email = requiredParameter("Email")
) {
  console.log(email);
}

createUser();
```

Error:

```text
Error: Email is required
```

Correct call:

```javascript
createUser("niket@example.com");
```

Output:

```text
niket@example.com
```

---

## Error 5: Wrong Parameter Order

This code is valid but can be confusing:

```javascript
function createProduct(
  category = "General",
  productName
) {
  console.log(category, productName);
}
```

To provide only the product name, we must write:

```javascript
createProduct(undefined, "Laptop");
```

A better parameter order is:

```javascript
function createProduct(
  productName,
  category = "General"
) {
  console.log(productName, category);
}

createProduct("Laptop");
```

Output:

```text
Laptop General
```

Required parameters should normally come before optional parameters.

---

# Default Parameter and Function Length

The `length` property returns the number of parameters before the first Default Parameter.

```javascript
function test(a, b, c = 10, d = 20) {}

console.log(test.length);
```

Output:

```text
2
```

Only `a` and `b` are counted because they appear before the first Default Parameter.

Another example:

```javascript
function example(a = 10, b, c) {}

console.log(example.length);
```

Output:

```text
0
```

The first parameter has a default value, so no parameters after it are counted.

---

# Best Practices

## 1. Put Required Parameters First

Recommended:

```javascript
function createUser(
  name,
  role = "user"
) {
  console.log(name, role);
}
```

Avoid:

```javascript
function createUser(
  role = "user",
  name
) {
  console.log(name, role);
}
```

---

## 2. Use Clear Default Values

Good:

```javascript
function getProducts(limit = 10) {
  console.log(limit);
}
```

The default value clearly shows that ten products will be returned.

---

## 3. Do Not Use Default Values to Hide Errors

For required information, validate the value or throw an error.

```javascript
function createOrder(productId) {
  if (!productId) {
    throw new Error("Product ID is required");
  }

  console.log("Order created");
}
```

---

## 4. Remember the Difference Between `undefined` and `null`

```text
undefined → Uses the default value

null → Does not use the default value
```

---

## 5. Keep Default Values Simple

Recommended:

```javascript
function calculateTax(
  price,
  rate = 0.18
) {
  return price * rate;
}
```

Avoid putting large and complicated calculations directly inside parameters.

---

# Default Parameters vs Logical OR

## Logical OR Method

```javascript
function showValue(value) {
  value = value || 100;

  console.log(value);
}

showValue(0);
```

Output:

```text
100
```

This is incorrect when `0` is a valid value.

## Default Parameter Method

```javascript
function showValue(value = 100) {
  console.log(value);
}

showValue(0);
```

Output:

```text
0
```

Default Parameters only activate for:

```text
Missing argument
undefined
```

They do not activate for:

```text
null
0
false
""
NaN
```

---

# Default Parameters vs Nullish Coalescing

Default Parameters do not replace `null`.

```javascript
function greet(name = "Guest") {
  console.log(name);
}

greet(null);
```

Output:

```text
null
```

To replace both `null` and `undefined`, use the Nullish Coalescing operator.

```javascript
function greet(name) {
  name = name ?? "Guest";

  console.log(name);
}

greet(null);
greet(undefined);
```

Output:

```text
Guest
Guest
```

Difference:

```text
Default Parameter:
Activates only for undefined or a missing argument.

Nullish Coalescing:
Activates for null and undefined.
```

---

# Interview Questions

## 1. What are Default Parameters?

Default Parameters allow us to assign a default value to a function parameter.

The default value is used when the function argument is missing or `undefined`.

---

## 2. In which JavaScript version were Default Parameters introduced?

Default Parameters were introduced in **ES6**, also known as **ECMAScript 2015**.

---

## 3. When does JavaScript use a Default Parameter?

JavaScript uses a Default Parameter when:

* No argument is passed.
* `undefined` is passed.

Example:

```javascript
function greet(name = "Guest") {
  console.log(name);
}

greet();
greet(undefined);
```

Both calls print:

```text
Guest
```

---

## 4. Does `null` activate a Default Parameter?

No.

`null` is treated as an actual value.

```javascript
function test(value = 10) {
  console.log(value);
}

test(null);
```

Output:

```text
null
```

---

## 5. Do `0`, `false`, and an empty string activate Default Parameters?

No.

They are valid values.

```javascript
function test(value = 100) {
  console.log(value);
}

test(0);
test(false);
test("");
```

Output:

```text
0
false

```

---

## 6. Can one Default Parameter use another parameter?

Yes, but it can only use a parameter declared before it.

```javascript
function calculate(
  price,
  tax = price * 0.18
) {
  console.log(tax);
}
```

---

## 7. Can a Default Parameter call a function?

Yes.

```javascript
function getValue() {
  return 100;
}

function test(value = getValue()) {
  console.log(value);
}
```

---

## 8. Can we use Default Parameters in Arrow Functions?

Yes.

```javascript
const add = (a = 10, b = 20) => a + b;

console.log(add());
```

Output:

```text
30
```

---

## 9. What is the difference between Default Parameters and `||`?

The logical OR operator replaces all falsy values.

Default Parameters only replace a missing argument or `undefined`.

Falsy values include:

```text
false
0
""
null
undefined
NaN
```

---

## 10. What error occurs when an earlier parameter uses a later parameter?

A `ReferenceError` occurs.

```javascript
function test(a = b, b = 10) {
  console.log(a, b);
}

test();
```

Error:

```text
ReferenceError: Cannot access 'b' before initialization
```

---

# Practice Questions

## Question 1

What will be the output?

```javascript
function greet(name = "Guest") {
  console.log(name);
}

greet();
```

Answer:

```text
Guest
```

---

## Question 2

What will be the output?

```javascript
function showNumber(number = 10) {
  console.log(number);
}

showNumber(0);
```

Answer:

```text
0
```

---

## Question 3

What will be the output?

```javascript
function test(value = 100) {
  console.log(value);
}

test(undefined);
test(null);
```

Answer:

```text
100
null
```

---

## Question 4

What will be the output?

```javascript
function add(a = 5, b = 10) {
  console.log(a + b);
}

add(20);
```

Answer:

```text
30
```

Explanation:

```text
a = 20
b = 10

20 + 10 = 30
```

---

## Question 5

Find the error:

```javascript
function test(a = b, b = 20) {
  console.log(a, b);
}

test();
```

Answer:

```text
ReferenceError: Cannot access 'b' before initialization
```

`a` cannot use `b` because `b` is declared later.

Correct code:

```javascript
function test(a = 20, b = a) {
  console.log(a, b);
}

test();
```

Output:

```text
20 20
```

---

# Practice Programs

## Program 1: Greeting Function

```javascript
function greetUser(
  name = "Guest",
  message = "Welcome"
) {
  console.log(`${message}, ${name}!`);
}

greetUser();
greetUser("Niket");
greetUser("Niket", "Good morning");
```

Output:

```text
Welcome, Guest!
Welcome, Niket!
Good morning, Niket!
```

---

## Program 2: Calculate Salary

```javascript
function calculateSalary(
  basicSalary,
  bonus = 0,
  taxRate = 10
) {
  const totalSalary =
    basicSalary + bonus;

  const tax =
    totalSalary * taxRate / 100;

  const finalSalary =
    totalSalary - tax;

  console.log("Final Salary:", finalSalary);
}

calculateSalary(50000);
calculateSalary(50000, 5000);
calculateSalary(50000, 5000, 5);
```

---

## Program 3: Create Product

```javascript
function createProduct(
  name,
  price,
  category = "General",
  stock = 0
) {
  return {
    name,
    price,
    category,
    stock
  };
}

console.log(
  createProduct("Laptop", 50000)
);
```

Output:

```javascript
{
  name: "Laptop",
  price: 50000,
  category: "General",
  stock: 0
}
```

---

# Summary

* Default Parameters provide fallback values to function parameters.
* They were introduced in ES6.
* The default value is used when an argument is missing.
* The default value is also used when `undefined` is passed.
* `null` does not activate a Default Parameter.
* `0`, `false`, `""`, and `NaN` do not activate Default Parameters.
* A parameter can use a previous parameter as its default value.
* A parameter cannot use another parameter declared after it.
* Default Parameters work with normal functions, Function Expressions, and Arrow Functions.
* Required parameters should normally be written before optional parameters.
* Default Parameters make functions cleaner, safer, and easier to understand.