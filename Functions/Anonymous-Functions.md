# Anonymous Functions in JavaScript

## What is an Anonymous Function?

An **anonymous function** is a function that does not have a name.

Normal function:

```javascript
function greet() {
  console.log("Hello");
}
```

Here, the function name is:

```text
greet
```

Anonymous function:

```javascript
function () {
  console.log("Hello");
}
```

This function does not have a name, so it is called an anonymous function.

However, writing an anonymous function alone gives an error.

Wrong:

```javascript
function () {
  console.log("Hello");
}
```

Error:

```text
SyntaxError: Function statements require a function name
```

Anonymous functions are usually:

* Stored inside variables
* Passed as callback functions
* Used with array methods
* Used with event listeners
* Used with `setTimeout()`
* Used inside an IIFE

---

# 1. Store an Anonymous Function in a Variable

```javascript
const greet = function () {
  console.log("Hello");
};

greet();
```

Output:

```text
Hello
```

Explanation:

```javascript
const greet = function () {
  console.log("Hello");
};
```

* `const greet` creates a variable.
* `function ()` creates an anonymous function.
* The anonymous function is stored inside `greet`.
* `greet()` calls the function.

The function itself has no name, but the variable name is `greet`.

---

# 2. Anonymous Function with Parameters

Anonymous functions can accept parameters.

```javascript
const add = function (a, b) {
  return a + b;
};

console.log(add(10, 20));
```

Output:

```text
30
```

Here:

```javascript
function (a, b)
```

* `a` is the first parameter.
* `b` is the second parameter.

When we call:

```javascript
add(10, 20);
```

JavaScript stores:

```text
a = 10
b = 20
```

Then:

```javascript
return a + b;
```

returns:

```text
30
```

---

# 3. Anonymous Function as a Callback

A function passed to another function is called a callback function.

```javascript
setTimeout(function () {
  console.log("Message displayed after 2 seconds");
}, 2000);
```

Output after 2 seconds:

```text
Message displayed after 2 seconds
```

This part is the anonymous function:

```javascript
function () {
  console.log("Message displayed after 2 seconds");
}
```

The value:

```javascript
2000
```

means 2000 milliseconds.

```text
1000 milliseconds = 1 second
2000 milliseconds = 2 seconds
```

---

# 4. Anonymous Function with setInterval()

`setInterval()` runs a function repeatedly.

```javascript
setInterval(function () {
  console.log("Hello");
}, 1000);
```

Output:

```text
Hello
Hello
Hello
Hello
```

The message prints every 1 second.

---

# 5. Anonymous Function in an Event Listener

Anonymous functions are commonly used with browser events.

HTML:

```html
<button id="btn">Click Me</button>
```

JavaScript:

```javascript
const button = document.getElementById("btn");

button.addEventListener("click", function () {
  console.log("Button clicked");
});
```

Output after clicking the button:

```text
Button clicked
```

The anonymous function runs when the user clicks the button.

---

# 6. Anonymous Function with forEach()

The `forEach()` method runs a function for every array element.

```javascript
const numbers = [10, 20, 30];

numbers.forEach(function (number) {
  console.log(number);
});
```

Output:

```text
10
20
30
```

Execution:

```text
First time: number = 10
Second time: number = 20
Third time: number = 30
```

---

# 7. Anonymous Function with map()

The `map()` method creates a new array.

```javascript
const numbers = [1, 2, 3, 4];

const doubledNumbers = numbers.map(function (number) {
  return number * 2;
});

console.log(doubledNumbers);
```

Output:

```text
[2, 4, 6, 8]
```

Process:

```text
1 × 2 = 2
2 × 2 = 4
3 × 2 = 6
4 × 2 = 8
```

The original array is not changed.

```javascript
console.log(numbers);
```

Output:

```text
[1, 2, 3, 4]
```

---

# 8. Anonymous Function with filter()

The `filter()` method returns values that satisfy a condition.

```javascript
const ages = [12, 18, 25, 15, 30];

const adults = ages.filter(function (age) {
  return age >= 18;
});

console.log(adults);
```

Output:

```text
[18, 25, 30]
```

The condition is:

```javascript
age >= 18
```

Only ages greater than or equal to 18 are added to the new array.

---

# 9. Anonymous Function with find()

The `find()` method returns the first matching value.

```javascript
const numbers = [5, 10, 15, 20];

const result = numbers.find(function (number) {
  return number > 10;
});

console.log(result);
```

Output:

```text
15
```

`15` is the first value greater than `10`.

---

# 10. Anonymous Function Passed to Another Function

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

Here:

```javascript
function (x, y) {
  return x + y;
}
```

is passed as an argument.

Inside `calculate()`:

```javascript
return operation(a, b);
```

JavaScript calls:

```javascript
operation(10, 5);
```

The result is:

```text
15
```

---

# 11. Immediately Invoked Anonymous Function

An anonymous function can run immediately after it is created.

This is called an IIFE.

IIFE means:

```text
Immediately Invoked Function Expression
```

Example:

```javascript
(function () {
  console.log("This function runs immediately");
})();
```

Output:

```text
This function runs immediately
```

Explanation:

```javascript
(function () {
  console.log("This function runs immediately");
})
```

creates the function.

The final parentheses:

```javascript
()
```

call the function immediately.

---

# 12. Anonymous Function Returning a Value

```javascript
const multiply = function (a, b) {
  return a * b;
};

const answer = multiply(5, 4);

console.log(answer);
```

Output:

```text
20
```

---

# 13. Anonymous Function Returning an Object

```javascript
const createUser = function (name, age) {
  return {
    name: name,
    age: age,
  };
};

const user = createUser("Niket", 21);

console.log(user);
```

Output:

```javascript
{
  name: "Niket",
  age: 21
}
```

---

# 14. Anonymous Function Inside an Object

```javascript
const user = {
  name: "Niket",

  showName: function () {
    console.log(this.name);
  },
};

user.showName();
```

Output:

```text
Niket
```

Here:

```javascript
function () {
  console.log(this.name);
}
```

is an anonymous function stored as an object method.

---

# Anonymous Function vs Named Function

## Named Function

```javascript
function greet() {
  console.log("Hello");
}
```

The function name is:

```text
greet
```

## Anonymous Function

```javascript
const greet = function () {
  console.log("Hello");
};
```

The function itself does not have a name.

It is stored inside the `greet` variable.

---

# Anonymous Function vs Arrow Function

Anonymous function:

```javascript
const add = function (a, b) {
  return a + b;
};
```

Arrow function:

```javascript
const add = (a, b) => {
  return a + b;
};
```

Short arrow function:

```javascript
const add = (a, b) => a + b;
```

All three examples return the sum of `a` and `b`.

---

# Hoisting Difference

A function declaration can be called before its definition.

```javascript
greet();

function greet() {
  console.log("Hello");
}
```

Output:

```text
Hello
```

But an anonymous function stored in `const` cannot be called before assignment.

Wrong:

```javascript
greet();

const greet = function () {
  console.log("Hello");
};
```

Error:

```text
ReferenceError: Cannot access 'greet' before initialization
```

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};

greet();
```

Output:

```text
Hello
```

---

# Common Errors in Anonymous Functions

## Error 1: Function Without a Name

Wrong:

```javascript
function () {
  console.log("Hello");
}
```

Error:

```text
SyntaxError: Function statements require a function name
```

Reason:

A normal function declaration must have a name.

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};
```

You can also use an IIFE:

```javascript
(function () {
  console.log("Hello");
})();
```

---

## Error 2: Calling Before Initialization

Wrong:

```javascript
sayHello();

const sayHello = function () {
  console.log("Hello");
};
```

Error:

```text
ReferenceError: Cannot access 'sayHello' before initialization
```

Correct:

```javascript
const sayHello = function () {
  console.log("Hello");
};

sayHello();
```

---

## Error 3: Forgetting Parentheses While Calling

Wrong:

```javascript
const greet = function () {
  console.log("Hello");
};

greet;
```

Output:

```text
No output
```

Reason:

```javascript
greet
```

only refers to the function.

It does not execute the function.

Correct:

```javascript
greet();
```

Output:

```text
Hello
```

---

## Error 4: Calling a Non-Function Value

Wrong:

```javascript
const greet = "Hello";

greet();
```

Error:

```text
TypeError: greet is not a function
```

Reason:

The `greet` variable contains a string, not a function.

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};

greet();
```

---

## Error 5: Missing return

Wrong:

```javascript
const add = function (a, b) {
  a + b;
};

console.log(add(10, 20));
```

Output:

```text
undefined
```

Reason:

The function calculates the value but does not return it.

Correct:

```javascript
const add = function (a, b) {
  return a + b;
};

console.log(add(10, 20));
```

Output:

```text
30
```

---

## Error 6: Missing Argument

```javascript
const add = function (a, b) {
  return a + b;
};

console.log(add(10));
```

Output:

```text
NaN
```

Reason:

JavaScript stores:

```text
a = 10
b = undefined
```

Then JavaScript calculates:

```javascript
10 + undefined
```

The result is:

```text
NaN
```

Correct:

```javascript
console.log(add(10, 20));
```

Output:

```text
30
```

You can also use a default parameter:

```javascript
const add = function (a, b = 0) {
  return a + b;
};

console.log(add(10));
```

Output:

```text
10
```

---

## Error 7: Incorrect Callback Syntax

Wrong:

```javascript
setTimeout(function {
  console.log("Hello");
}, 1000);
```

Error:

```text
SyntaxError: Unexpected token '{'
```

Reason:

Parentheses are required after the `function` keyword.

Correct:

```javascript
setTimeout(function () {
  console.log("Hello");
}, 1000);
```

---

## Error 8: Calling a Function Immediately Instead of Passing It

```javascript
function showMessage() {
  console.log("Hello");
}
```

Wrong:

```javascript
setTimeout(showMessage(), 2000);
```

In this code, `showMessage()` runs immediately.

Correct:

```javascript
setTimeout(showMessage, 2000);
```

Or:

```javascript
setTimeout(function () {
  showMessage();
}, 2000);
```

Now the function runs after 2 seconds.

---

## Error 9: Variable Scope Error

Wrong:

```javascript
const showMessage = function () {
  let message = "Hello";
};

showMessage();

console.log(message);
```

Error:

```text
ReferenceError: message is not defined
```

Reason:

The `message` variable only exists inside the function.

Correct:

```javascript
const showMessage = function () {
  let message = "Hello";

  console.log(message);
};

showMessage();
```

Output:

```text
Hello
```

---

## Error 10: Missing Closing Bracket

Wrong:

```javascript
const greet = function () {
  console.log("Hello");
;
```

Error:

```text
SyntaxError: Unexpected end of input
```

Correct:

```javascript
const greet = function () {
  console.log("Hello");
};
```

---

## Error 11: Missing Comma in Callback Arguments

Wrong:

```javascript
setTimeout(function () {
  console.log("Hello");
} 1000);
```

Error:

```text
SyntaxError: missing ) after argument list
```

Correct:

```javascript
setTimeout(function () {
  console.log("Hello");
}, 1000);
```

---

## Error 12: Reassigning a const Function

Wrong:

```javascript
const greet = function () {
  console.log("Hello");
};

greet = function () {
  console.log("Hi");
};
```

Error:

```text
TypeError: Assignment to constant variable
```

Reason:

A variable created with `const` cannot be reassigned.

You can use `let` when reassignment is required.

```javascript
let greet = function () {
  console.log("Hello");
};

greet = function () {
  console.log("Hi");
};

greet();
```

Output:

```text
Hi
```

---

# Practical Example: Calculator

```javascript
const calculate = function (number1, number2, operation) {
  return operation(number1, number2);
};

const addition = calculate(20, 10, function (a, b) {
  return a + b;
});

const subtraction = calculate(20, 10, function (a, b) {
  return a - b;
});

const multiplication = calculate(20, 10, function (a, b) {
  return a * b;
});

const division = calculate(20, 10, function (a, b) {
  return a / b;
});

console.log("Addition:", addition);
console.log("Subtraction:", subtraction);
console.log("Multiplication:", multiplication);
console.log("Division:", division);
```

Output:

```text
Addition: 30
Subtraction: 10
Multiplication: 200
Division: 2
```

---

# Practical Example: Find Passed Students

```javascript
const students = [
  {
    name: "Niket",
    marks: 80,
  },
  {
    name: "Rahul",
    marks: 30,
  },
  {
    name: "Priya",
    marks: 70,
  },
  {
    name: "Amit",
    marks: 25,
  },
];

const passedStudents = students.filter(function (student) {
  return student.marks >= 35;
});

console.log(passedStudents);
```

Output:

```javascript
[
  {
    name: "Niket",
    marks: 80
  },
  {
    name: "Priya",
    marks: 70
  }
]
```

---

# Practical Example: Get Adult User Names

```javascript
const users = [
  {
    name: "Niket",
    age: 21,
  },
  {
    name: "Rahul",
    age: 16,
  },
  {
    name: "Priya",
    age: 25,
  },
];

const adultNames = users
  .filter(function (user) {
    return user.age >= 18;
  })
  .map(function (user) {
    return user.name;
  });

console.log(adultNames);
```

Output:

```text
["Niket", "Priya"]
```

The first anonymous function filters adult users.

```javascript
function (user) {
  return user.age >= 18;
}
```

The second anonymous function returns only their names.

```javascript
function (user) {
  return user.name;
}
```

---

# Advantages of Anonymous Functions

Anonymous functions are useful because:

* They are good for small tasks.
* They reduce unnecessary function names.
* They work well as callbacks.
* They are commonly used with array methods.
* They are useful in event listeners.
* They can be passed to other functions.
* They can be returned from functions.
* They are useful when a function is used only once.

---

# Disadvantages of Anonymous Functions

Anonymous functions also have some disadvantages:

* Debugging can be more difficult.
* Large anonymous functions reduce readability.
* They cannot be called before assignment when stored in `let` or `const`.
* Reusing them can be difficult.
* Too many nested anonymous functions can make code confusing.

Bad example:

```javascript
button.addEventListener("click", function () {
  setTimeout(function () {
    numbers.forEach(function (number) {
      console.log(number);
    });
  }, 1000);
});
```

Better example using named functions:

```javascript
function printNumber(number) {
  console.log(number);
}

function printNumbers() {
  numbers.forEach(printNumber);
}

function handleClick() {
  setTimeout(printNumbers, 1000);
}

button.addEventListener("click", handleClick);
```

---

# When Should You Use Anonymous Functions?

Use anonymous functions when:

* The function is small.
* The function is used only once.
* You are using `map()`.
* You are using `filter()`.
* You are using `forEach()`.
* You are handling a browser event.
* You are passing a callback.
* You are using `setTimeout()`.
* You are using `setInterval()`.

Use named functions when:

* The function is large.
* The function is reused many times.
* Better debugging is required.
* The function has an important purpose.
* You want more readable code.

---

# Interview Questions

## 1. What is an anonymous function?

An anonymous function is a function without a name.

```javascript
const greet = function () {
  console.log("Hello");
};
```

---

## 2. Can an anonymous function run by itself?

An anonymous function cannot be written alone like a normal function declaration.

Wrong:

```javascript
function () {
  console.log("Hello");
}
```

It must be:

* Stored in a variable
* Passed as a callback
* Used inside an IIFE
* Passed as an argument

---

## 3. Are anonymous functions hoisted?

An anonymous function stored in `const` or `let` cannot be used before assignment.

```javascript
const greet = function () {
  console.log("Hello");
};
```

Calling `greet()` before this line gives an error.

---

## 4. Where are anonymous functions commonly used?

Anonymous functions are commonly used with:

```text
setTimeout()
setInterval()
forEach()
map()
filter()
find()
event listeners
callbacks
IIFE
```

---

## 5. What is the difference between a named and anonymous function?

Named function:

```javascript
function greet() {
  console.log("Hello");
}
```

Anonymous function:

```javascript
const greet = function () {
  console.log("Hello");
};
```

A named function has its own name.

An anonymous function does not have its own name.

---

## 6. What is the difference between an anonymous function and an arrow function?

Anonymous function:

```javascript
const greet = function () {
  console.log("Hello");
};
```

Arrow function:

```javascript
const greet = () => {
  console.log("Hello");
};
```

Arrow functions do not have their own:

```text
this
arguments
prototype
```

---

## 7. Can an anonymous function return a value?

Yes.

```javascript
const add = function (a, b) {
  return a + b;
};

console.log(add(5, 5));
```

Output:

```text
10
```

---

## 8. Can an anonymous function accept parameters?

Yes.

```javascript
const greet = function (name) {
  console.log("Hello " + name);
};

greet("Niket");
```

Output:

```text
Hello Niket
```

---

# Final Summary

An anonymous function is a function without a name.

Basic syntax:

```javascript
const functionName = function () {
  // code
};
```

Example:

```javascript
const greet = function () {
  console.log("Hello");
};

greet();
```

Output:

```text
Hello
```

Anonymous functions are mainly used with:

```text
Variables
Callbacks
Array methods
Event listeners
setTimeout()
setInterval()
IIFE
```

Important points:

* Anonymous functions have no function name.
* They can be stored inside variables.
* They can accept parameters.
* They can return values.
* They are often used as callbacks.
* They cannot normally be called before assignment.
* Large anonymous functions can make code difficult to understand.
