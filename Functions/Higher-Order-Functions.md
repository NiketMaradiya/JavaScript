# Higher-Order Functions in JavaScript

## What is a Higher-Order Function?

A **Higher-Order Function** is a function that:

1. Takes another function as an argument.
2. Returns another function.
3. Or does both.

Simple definition:

> A function that works with another function is called a Higher-Order Function.

---

## Basic Example

```javascript
function greet(name) {
  return `Hello, ${name}`;
}

function displayMessage(callback) {
  console.log(callback("Niket"));
}

displayMessage(greet);
```

Output:

```text
Hello, Niket
```

Explanation:

* `greet` is passed as an argument.
* `displayMessage` accepts another function.
* Therefore, `displayMessage` is a Higher-Order Function.
* `greet` is a callback function.

---

# Why Do We Use Higher-Order Functions?

Higher-Order Functions help us:

* Reuse code.
* Reduce repeated code.
* Make code flexible.
* Make programs easier to maintain.
* Work with arrays.
* Handle asynchronous operations.

---

# 1. Passing a Function as an Argument

```javascript
function sayHello() {
  console.log("Hello");
}

function executeFunction(callback) {
  callback();
}

executeFunction(sayHello);
```

Output:

```text
Hello
```

Here:

```javascript
executeFunction(sayHello);
```

We pass the `sayHello` function without calling it.

Inside the function:

```javascript
callback();
```

This executes `sayHello()`.

---

# Passing a Function vs Calling a Function

Pass a function:

```javascript
sayHello
```

Call a function:

```javascript
sayHello()
```

Correct:

```javascript
executeFunction(sayHello);
```

Incorrect:

```javascript
executeFunction(sayHello());
```

Why?

Because `sayHello()` runs immediately and its return value is passed.

---

# Calculation Example

```javascript
function add(a, b) {
  return a + b;
}

function calculate(num1, num2, operation) {
  return operation(num1, num2);
}

const result = calculate(10, 5, add);

console.log(result);
```

Output:

```text
15
```

Explanation:

```javascript
calculate(10, 5, add);
```

Inside `calculate`:

```javascript
return operation(num1, num2);
```

This becomes:

```javascript
return add(10, 5);
```

---

# Multiple Operations

```javascript
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

function multiply(a, b) {
  return a * b;
}

function divide(a, b) {
  return a / b;
}

function calculate(a, b, operation) {
  return operation(a, b);
}

console.log(calculate(10, 5, add));
console.log(calculate(10, 5, subtract));
console.log(calculate(10, 5, multiply));
console.log(calculate(10, 5, divide));
```

Output:

```text
15
5
50
2
```

---

# Using an Anonymous Function

```javascript
function calculate(a, b, operation) {
  return operation(a, b);
}

const result = calculate(10, 5, function (x, y) {
  return x + y;
});

console.log(result);
```

Output:

```text
15
```

---

# Using an Arrow Function

```javascript
function calculate(a, b, operation) {
  return operation(a, b);
}

const result = calculate(10, 5, (x, y) => x * y);

console.log(result);
```

Output:

```text
50
```

---

# 2. Returning a Function

A Higher-Order Function can return another function.

```javascript
function createGreeting() {
  return function () {
    console.log("Hello, welcome!");
  };
}

const greeting = createGreeting();

greeting();
```

Output:

```text
Hello, welcome!
```

Explanation:

```javascript
const greeting = createGreeting();
```

The returned function is stored in `greeting`.

Then:

```javascript
greeting();
```

executes the returned function.

---

# Returning a Function with Data

```javascript
function greetPerson(name) {
  return function () {
    console.log(`Hello, ${name}`);
  };
}

const greetNiket = greetPerson("Niket");
const greetRahul = greetPerson("Rahul");

greetNiket();
greetRahul();
```

Output:

```text
Hello, Niket
Hello, Rahul
```

The returned function remembers the `name`.

This is related to a JavaScript concept called **Closure**.

---

# Multiplier Example

```javascript
function createMultiplier(number) {
  return function (value) {
    return value * number;
  };
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(10));
console.log(triple(10));
```

Output:

```text
20
30
```

---

# Age Checker Example

```javascript
function createAgeChecker(minimumAge) {
  return function (age) {
    return age >= minimumAge;
  };
}

const canVote = createAgeChecker(18);
const canDrive = createAgeChecker(16);

console.log(canVote(20));
console.log(canVote(15));

console.log(canDrive(17));
console.log(canDrive(14));
```

Output:

```text
true
false
true
false
```

---

# Higher-Order Functions with Arrays

JavaScript has many built-in Higher-Order Functions:

* `forEach()`
* `map()`
* `filter()`
* `reduce()`
* `find()`
* `some()`
* `every()`
* `sort()`

These methods accept callback functions.

---

# forEach() Example

`forEach()` executes a function for every array item.

```javascript
const numbers = [10, 20, 30];

numbers.forEach((number) => {
  console.log(number);
});
```

Output:

```text
10
20
30
```

---

# map() Example

`map()` creates a new array by changing every value.

```javascript
const numbers = [1, 2, 3, 4];

const doubledNumbers = numbers.map((number) => {
  return number * 2;
});

console.log(doubledNumbers);
```

Output:

```text
[2, 4, 6, 8]
```

The original array is not changed.

---

# filter() Example

`filter()` creates a new array containing values that pass a condition.

```javascript
const ages = [12, 18, 20, 15, 25];

const adults = ages.filter((age) => {
  return age >= 18;
});

console.log(adults);
```

Output:

```text
[18, 20, 25]
```

---

# reduce() Example

`reduce()` combines all array values into one value.

```javascript
const numbers = [10, 20, 30];

const total = numbers.reduce((sum, number) => {
  return sum + number;
}, 0);

console.log(total);
```

Output:

```text
60
```

Process:

```text
0 + 10 = 10
10 + 20 = 30
30 + 30 = 60
```

---

# find() Example

`find()` returns the first value that matches a condition.

```javascript
const numbers = [5, 12, 8, 20];

const result = numbers.find((number) => {
  return number > 10;
});

console.log(result);
```

Output:

```text
12
```

---

# Custom Higher-Order Function

```javascript
function processArray(array, callback) {
  const result = [];

  for (const item of array) {
    result.push(callback(item));
  }

  return result;
}

const numbers = [1, 2, 3, 4];

const doubled = processArray(numbers, (number) => {
  return number * 2;
});

console.log(doubled);
```

Output:

```text
[2, 4, 6, 8]
```

---

# Real-Life Example: Employee Bonus

```javascript
const employees = [
  { name: "Niket", salary: 30000 },
  { name: "Rahul", salary: 40000 },
  { name: "Priya", salary: 50000 }
];

const updatedEmployees = employees.map((employee) => {
  return {
    name: employee.name,
    salary: employee.salary,
    bonus: employee.salary * 0.1
  };
});

console.log(updatedEmployees);
```

Output:

```javascript
[
  {
    name: "Niket",
    salary: 30000,
    bonus: 3000
  },
  {
    name: "Rahul",
    salary: 40000,
    bonus: 4000
  },
  {
    name: "Priya",
    salary: 50000,
    bonus: 5000
  }
]
```

---

# Real-Life Example: User Permission

```javascript
function checkPermission(requiredRole) {
  return function (user) {
    return user.role === requiredRole;
  };
}

const isAdmin = checkPermission("admin");
const isManager = checkPermission("manager");

const user1 = {
  name: "Niket",
  role: "admin"
};

const user2 = {
  name: "Rahul",
  role: "employee"
};

console.log(isAdmin(user1));
console.log(isAdmin(user2));
console.log(isManager(user1));
```

Output:

```text
true
false
false
```

---

# Common Errors

## Error 1: Callback Is Not a Function

Incorrect:

```javascript
function execute(callback) {
  callback();
}

execute("Hello");
```

Error:

```text
TypeError: callback is not a function
```

Reason:

`"Hello"` is a string, not a function.

Correct:

```javascript
function execute(callback) {
  callback();
}

execute(function () {
  console.log("Hello");
});
```

Output:

```text
Hello
```

Safer version:

```javascript
function execute(callback) {
  if (typeof callback !== "function") {
    console.log("Please provide a valid function");
    return;
  }

  callback();
}

execute("Hello");
```

Output:

```text
Please provide a valid function
```

---

## Error 2: Calling Instead of Passing

Incorrect:

```javascript
function greet() {
  console.log("Hello");
}

function execute(callback) {
  callback();
}

execute(greet());
```

Output and error:

```text
Hello
TypeError: callback is not a function
```

Reason:

```javascript
greet()
```

runs immediately and returns `undefined`.

The code becomes:

```javascript
execute(undefined);
```

Correct:

```javascript
execute(greet);
```

---

## Error 3: Forgetting to Call the Callback

Incorrect:

```javascript
function calculate(a, b, operation) {
  return operation;
}

function add(a, b) {
  return a + b;
}

console.log(calculate(10, 5, add));
```

Output:

```text
[Function: add]
```

Correct:

```javascript
function calculate(a, b, operation) {
  return operation(a, b);
}
```

Output:

```text
15
```

---

## Error 4: Missing return in map()

Incorrect:

```javascript
const numbers = [1, 2, 3];

const doubled = numbers.map((number) => {
  number * 2;
});

console.log(doubled);
```

Output:

```text
[undefined, undefined, undefined]
```

Reason:

When using `{}`, you must write `return`.

Correct:

```javascript
const doubled = numbers.map((number) => {
  return number * 2;
});
```

Short form:

```javascript
const doubled = numbers.map((number) => number * 2);
```

Output:

```text
[2, 4, 6]
```

---

## Error 5: Missing return in filter()

Incorrect:

```javascript
const numbers = [1, 2, 3, 4];

const evenNumbers = numbers.filter((number) => {
  number % 2 === 0;
});

console.log(evenNumbers);
```

Output:

```text
[]
```

Correct:

```javascript
const evenNumbers = numbers.filter((number) => {
  return number % 2 === 0;
});
```

Output:

```text
[2, 4]
```

---

## Error 6: Callback Not Provided

Incorrect:

```javascript
function calculate(a, b, operation) {
  return operation(a, b);
}

calculate(10, 5);
```

Error:

```text
TypeError: operation is not a function
```

Reason:

The third argument is missing.

Correct:

```javascript
const result = calculate(10, 5, (a, b) => a + b);

console.log(result);
```

Output:

```text
15
```

Safer version:

```javascript
function calculate(a, b, operation) {
  if (typeof operation !== "function") {
    throw new TypeError("Operation must be a function");
  }

  return operation(a, b);
}
```

---

## Error 7: Returning a Value Instead of a Function

Incorrect:

```javascript
function createMultiplier(number) {
  return number * 2;
}

const double = createMultiplier(2);

console.log(double(10));
```

Error:

```text
TypeError: double is not a function
```

Reason:

```javascript
createMultiplier(2)
```

returns `4`, not a function.

Correct:

```javascript
function createMultiplier(number) {
  return function (value) {
    return value * number;
  };
}
```

---

## Error 8: Confusing map() and forEach()

Incorrect:

```javascript
const numbers = [1, 2, 3];

const result = numbers.forEach((number) => {
  return number * 2;
});

console.log(result);
```

Output:

```text
undefined
```

Reason:

`forEach()` does not return a new array.

Correct:

```javascript
const result = numbers.map((number) => {
  return number * 2;
});

console.log(result);
```

Output:

```text
[2, 4, 6]
```

---

## Error 9: this Problem in Callback

Incorrect:

```javascript
const user = {
  name: "Niket",

  showName: function () {
    setTimeout(function () {
      console.log(this.name);
    }, 1000);
  }
};

user.showName();
```

Possible output:

```text
undefined
```

Correct:

```javascript
const user = {
  name: "Niket",

  showName: function () {
    setTimeout(() => {
      console.log(this.name);
    }, 1000);
  }
};

user.showName();
```

Output:

```text
Niket
```

The arrow function uses `this` from the outer function.

---

# Synchronous Higher-Order Function

A synchronous callback runs immediately.

```javascript
function processData(callback) {
  console.log("Processing started");

  callback();

  console.log("Processing finished");
}

processData(() => {
  console.log("Data processed");
});
```

Output:

```text
Processing started
Data processed
Processing finished
```

---

# Asynchronous Higher-Order Function

An asynchronous callback runs later.

```javascript
function processData(callback) {
  console.log("Processing started");

  setTimeout(() => {
    callback();
  }, 2000);

  console.log("Processing function finished");
}

processData(() => {
  console.log("Data processed");
});
```

Output:

```text
Processing started
Processing function finished
Data processed
```

`setTimeout()` is also a Higher-Order Function.

---

# Error Handling with a Callback

```javascript
function divide(a, b, callback) {
  if (b === 0) {
    callback(new Error("Cannot divide by zero"), null);
    return;
  }

  const result = a / b;

  callback(null, result);
}

divide(10, 2, (error, result) => {
  if (error) {
    console.log(error.message);
    return;
  }

  console.log(result);
});
```

Output:

```text
5
```

Divide by zero:

```javascript
divide(10, 0, (error, result) => {
  if (error) {
    console.log(error.message);
    return;
  }

  console.log(result);
});
```

Output:

```text
Cannot divide by zero
```

---

# Higher-Order Function vs Callback Function

```javascript
function greet(name) {
  return `Hello, ${name}`;
}

function display(callback) {
  console.log(callback("Niket"));
}

display(greet);
```

Here:

* `display` is a Higher-Order Function.
* `greet` is a callback function.

A Higher-Order Function receives or returns another function.

A callback function is passed into another function.

---

# Normal Function vs Higher-Order Function

Normal function:

```javascript
function add(a, b) {
  return a + b;
}

console.log(add(10, 5));
```

Higher-Order Function:

```javascript
function calculate(a, b, operation) {
  return operation(a, b);
}

console.log(calculate(10, 5, add));
```

---

# Complete Practical Example

```javascript
const students = [
  { name: "Niket", marks: 85 },
  { name: "Rahul", marks: 45 },
  { name: "Priya", marks: 75 },
  { name: "Amit", marks: 30 }
];

const passedStudents = students.filter((student) => {
  return student.marks >= 50;
});

const studentNames = passedStudents.map((student) => {
  return student.name;
});

console.log(passedStudents);
console.log(studentNames);
```

Output:

```javascript
[
  { name: "Niket", marks: 85 },
  { name: "Priya", marks: 75 }
]
```

```javascript
["Niket", "Priya"]
```

---

# Interview Questions

## 1. What is a Higher-Order Function?

A Higher-Order Function is a function that accepts another function, returns another function, or does both.

---

## 2. What is a callback function?

A callback is a function passed as an argument to another function.

---

## 3. Is map() a Higher-Order Function?

Yes. `map()` accepts a callback function.

```javascript
const result = [1, 2, 3].map((number) => number * 2);
```

---

## 4. What is the difference between map() and forEach()?

* `map()` returns a new array.
* `forEach()` returns `undefined`.

---

## 5. What is the difference between passing and calling a function?

Passing:

```javascript
execute(greet);
```

Calling:

```javascript
execute(greet());
```

---

## 6. Can a function return another function?

Yes.

```javascript
function outer() {
  return function inner() {
    console.log("Inner function");
  };
}
```

---

## 7. Why are Higher-Order Functions useful?

They improve:

* Code reuse.
* Flexibility.
* Readability.
* Maintainability.
* Array processing.
* Asynchronous programming.

---

# Important Points

A Higher-Order Function:

* Accepts another function.
* Returns another function.
* Can do both.
* Helps reduce duplicate code.
* Makes code reusable.
* Is commonly used with arrays.
* Is commonly used in asynchronous programming.

Common Higher-Order Functions:

```javascript
forEach()
map()
filter()
reduce()
find()
some()
every()
sort()
setTimeout()
setInterval()
```

Remember:

```javascript
myFunction
```

passes the function.

```javascript
myFunction()
```

calls the function.
