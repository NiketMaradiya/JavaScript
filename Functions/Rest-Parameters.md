# JavaScript Rest Parameters

## What is a Rest Parameter?

A **rest parameter** allows a JavaScript function to accept any number of arguments.

It collects all remaining arguments into a single array.

Rest parameter uses three dots:

```javascript
...
```

Syntax:

```javascript
function functionName(...parameterName) {
  // code
}
```

Example:

```javascript
function showNumbers(...numbers) {
  console.log(numbers);
}

showNumbers(10, 20, 30, 40);
```

Output:

```text
[10, 20, 30, 40]
```

Here:

```javascript
...numbers
```

collects all arguments inside the `numbers` array.

---

## Why Do We Use Rest Parameters?

Normally, a function accepts a fixed number of parameters.

```javascript
function add(a, b) {
  return a + b;
}

console.log(add(10, 20));
```

Output:

```text
30
```

But sometimes we do not know how many values the user will provide.

Without rest parameters:

```javascript
function add(a, b, c, d, e) {
  return a + b + c + d + e;
}
```

This function accepts only five values.

Using a rest parameter:

```javascript
function add(...numbers) {
  let total = 0;

  for (const number of numbers) {
    total += number;
  }

  return total;
}

console.log(add(10, 20));
console.log(add(10, 20, 30));
console.log(add(10, 20, 30, 40, 50));
```

Output:

```text
30
60
150
```

Now the function can accept any number of arguments.

---

## Rest Parameter Creates an Array

The rest parameter stores all values inside a real JavaScript array.

```javascript
function test(...values) {
  console.log(values);
  console.log(Array.isArray(values));
}

test(10, 20, 30);
```

Output:

```text
[10, 20, 30]
true
```

Because it is an array, we can use array methods such as:

```text
map()
filter()
reduce()
forEach()
find()
some()
every()
```

Example using `reduce()`:

```javascript
function add(...numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, 20, 30, 40));
```

Output:

```text
100
```

---

## Rest Parameter with Normal Parameters

A rest parameter can be used with normal parameters.

```javascript
function studentDetails(name, age, ...subjects) {
  console.log("Name:", name);
  console.log("Age:", age);
  console.log("Subjects:", subjects);
}

studentDetails(
  "Niket",
  21,
  "JavaScript",
  "Node.js",
  "MongoDB"
);
```

Output:

```text
Name: Niket
Age: 21
Subjects: ["JavaScript", "Node.js", "MongoDB"]
```

Here:

```javascript
name
```

gets:

```text
Niket
```

The `age` parameter gets:

```text
21
```

The rest parameter:

```javascript
...subjects
```

collects all remaining values:

```text
["JavaScript", "Node.js", "MongoDB"]
```

---

## Rest Parameter Must Be Last

A rest parameter must always be the last parameter in a function.

Correct:

```javascript
function user(name, age, ...skills) {
  console.log(name);
  console.log(age);
  console.log(skills);
}
```

Incorrect:

```javascript
function user(...skills, name) {
  console.log(skills);
  console.log(name);
}
```

Error:

```text
SyntaxError: Rest parameter must be last formal parameter
```

JavaScript does not know how many values should be stored in `skills` and which value should be stored in `name`.

Therefore, the rest parameter must always come last.

---

## Only One Rest Parameter Is Allowed

You cannot use multiple rest parameters in the same function.

Incorrect:

```javascript
function details(...names, ...ages) {
  console.log(names);
  console.log(ages);
}
```

Error:

```text
SyntaxError: Rest parameter must be last formal parameter
```

Correct:

```javascript
function details(title, ...values) {
  console.log(title);
  console.log(values);
}

details(
  "Student Information",
  "Niket",
  21,
  "Ahmedabad"
);
```

Output:

```text
Student Information
["Niket", 21, "Ahmedabad"]
```

---

# Examples of Rest Parameters

## Example 1: Add Any Number of Values

```javascript
function calculateTotal(...numbers) {
  let total = 0;

  for (const number of numbers) {
    total += number;
  }

  return total;
}

console.log(calculateTotal(100, 200));
console.log(calculateTotal(100, 200, 300));
console.log(calculateTotal(10, 20, 30, 40, 50));
```

Output:

```text
300
600
150
```

---

## Example 2: Add Numbers Using `reduce()`

```javascript
function add(...numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, 20, 30));
```

Output:

```text
60
```

---

## Example 3: Find the Largest Number

```javascript
function findLargest(...numbers) {
  return Math.max(...numbers);
}

console.log(findLargest(10, 80, 30, 100, 25));
```

Output:

```text
100
```

In this example:

```javascript
function findLargest(...numbers)
```

`...numbers` is a rest parameter because it collects all arguments into an array.

In this line:

```javascript
Math.max(...numbers)
```

`...numbers` is the spread operator because it expands the array into separate values.

---

## Example 4: Find the Smallest Number

```javascript
function findSmallest(...numbers) {
  return Math.min(...numbers);
}

console.log(findSmallest(50, 10, 90, 5, 40));
```

Output:

```text
5
```

---

## Example 5: Calculate Average

```javascript
function calculateAverage(...numbers) {
  if (numbers.length === 0) {
    return 0;
  }

  const total = numbers.reduce((sum, number) => {
    return sum + number;
  }, 0);

  return total / numbers.length;
}

console.log(calculateAverage(10, 20, 30));
console.log(calculateAverage(50, 60, 70, 80));
```

Output:

```text
20
65
```

This condition checks whether no numbers were provided:

```javascript
if (numbers.length === 0) {
  return 0;
}
```

Without this condition:

```javascript
calculateAverage();
```

would calculate:

```text
0 / 0
```

Result:

```text
NaN
```

---

## Example 6: Separate First Value from Remaining Values

```javascript
function displayLanguages(
  firstLanguage,
  ...otherLanguages
) {
  console.log("First language:", firstLanguage);
  console.log("Other languages:", otherLanguages);
}

displayLanguages(
  "JavaScript",
  "Python",
  "Java",
  "C++"
);
```

Output:

```text
First language: JavaScript
Other languages: ["Python", "Java", "C++"]
```

---

## Example 7: Create User with Multiple Roles

```javascript
function createUser(username, ...roles) {
  return {
    username: username,
    roles: roles
  };
}

const user = createUser(
  "niket",
  "admin",
  "manager",
  "editor"
);

console.log(user);
```

Output:

```javascript
{
  username: "niket",
  roles: ["admin", "manager", "editor"]
}
```

---

## Example 8: Filter Even Numbers

```javascript
function getEvenNumbers(...numbers) {
  return numbers.filter((number) => {
    return number % 2 === 0;
  });
}

console.log(
  getEvenNumbers(1, 2, 3, 4, 5, 6, 8)
);
```

Output:

```text
[2, 4, 6, 8]
```

---

## Example 9: Filter Positive Numbers

```javascript
function getPositiveNumbers(...numbers) {
  return numbers.filter((number) => {
    return number > 0;
  });
}

console.log(
  getPositiveNumbers(-10, 5, -2, 20, 0, 7)
);
```

Output:

```text
[5, 20, 7]
```

---

## Example 10: Join Words into a Sentence

```javascript
function createSentence(...words) {
  return words.join(" ");
}

const sentence = createSentence(
  "JavaScript",
  "is",
  "easy",
  "to",
  "learn"
);

console.log(sentence);
```

Output:

```text
JavaScript is easy to learn
```

---

## Example 11: Shopping Cart Total

```javascript
function calculateCartTotal(
  customerName,
  ...prices
) {
  const total = prices.reduce((sum, price) => {
    return sum + price;
  }, 0);

  console.log("Customer:", customerName);
  console.log("Items:", prices);
  console.log("Total:", total);
}

calculateCartTotal(
  "Niket",
  500,
  250,
  100,
  150
);
```

Output:

```text
Customer: Niket
Items: [500, 250, 100, 150]
Total: 1000
```

---

## Rest Parameter in Arrow Functions

Rest parameters can also be used inside arrow functions.

```javascript
const add = (...numbers) => {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
};

console.log(add(10, 20, 30));
```

Output:

```text
60
```

Short form:

```javascript
const add = (...numbers) =>
  numbers.reduce(
    (total, number) => total + number,
    0
  );

console.log(add(5, 10, 15));
```

Output:

```text
30
```

---

## Rest Syntax in Array Destructuring

Rest syntax can collect remaining array values.

```javascript
const numbers = [10, 20, 30, 40, 50];

const [
  first,
  second,
  ...remainingNumbers
] = numbers;

console.log(first);
console.log(second);
console.log(remainingNumbers);
```

Output:

```text
10
20
[30, 40, 50]
```

Here:

```javascript
first
```

gets:

```text
10
```

The `second` variable gets:

```text
20
```

The rest variable:

```javascript
...remainingNumbers
```

gets:

```text
[30, 40, 50]
```

---

## Rest Syntax in Object Destructuring

Rest syntax can collect remaining object properties.

```javascript
const student = {
  name: "Niket",
  age: 21,
  city: "Ahmedabad",
  course: "Computer Engineering"
};

const {
  name,
  ...otherDetails
} = student;

console.log(name);
console.log(otherDetails);
```

Output:

```javascript
Niket

{
  age: 21,
  city: "Ahmedabad",
  course: "Computer Engineering"
}
```

The `name` property is stored separately.

All other properties are collected inside the `otherDetails` object.

---

# Rest Parameter vs Spread Operator

Both rest and spread use three dots:

```javascript
...
```

But their work is different.

## Rest Parameter

Rest collects multiple values into one array.

```javascript
function show(...numbers) {
  console.log(numbers);
}

show(10, 20, 30);
```

Output:

```text
[10, 20, 30]
```

Easy meaning:

```text
Multiple values → One array
```

---

## Spread Operator

Spread expands an array into separate values.

```javascript
const numbers = [10, 20, 30];

console.log(...numbers);
```

Output:

```text
10 20 30
```

Easy meaning:

```text
One array → Multiple values
```

---

## Rest and Spread in the Same Example

```javascript
function calculate(...numbers) {
  return Math.max(...numbers);
}

console.log(calculate(10, 50, 20, 90));
```

Output:

```text
90
```

Here:

```javascript
function calculate(...numbers)
```

is rest because it collects values.

Here:

```javascript
Math.max(...numbers)
```

is spread because it expands the array.

---

# Rest Parameter vs `arguments` Object

Before rest parameters, JavaScript used the `arguments` object.

```javascript
function showArguments() {
  console.log(arguments);
}

showArguments(10, 20, 30);
```

The `arguments` object stores all function arguments.

But `arguments` is not a real array.

```javascript
function test() {
  console.log(Array.isArray(arguments));
}

test(10, 20);
```

Output:

```text
false
```

A rest parameter is a real array.

```javascript
function test(...values) {
  console.log(Array.isArray(values));
}

test(10, 20);
```

Output:

```text
true
```

Because rest parameters create arrays, array methods can be used directly.

```javascript
function doubleValues(...values) {
  return values.map((value) => {
    return value * 2;
  });
}

console.log(doubleValues(10, 20, 30));
```

Output:

```text
[20, 40, 60]
```

---

## Arrow Functions and `arguments`

Arrow functions do not have their own `arguments` object.

Incorrect:

```javascript
const show = () => {
  console.log(arguments);
};

show(10, 20);
```

Possible error:

```text
ReferenceError: arguments is not defined
```

Use a rest parameter instead:

```javascript
const show = (...values) => {
  console.log(values);
};

show(10, 20);
```

Output:

```text
[10, 20]
```

---

# Common Rest Parameter Errors

## Error 1: Rest Parameter Is Not Last

Incorrect:

```javascript
function user(...skills, name) {
  console.log(skills);
  console.log(name);
}
```

Error:

```text
SyntaxError: Rest parameter must be last formal parameter
```

Correct:

```javascript
function user(name, ...skills) {
  console.log(name);
  console.log(skills);
}
```

---

## Error 2: Comma After Rest Parameter

Incorrect:

```javascript
function add(...numbers,) {
  console.log(numbers);
}
```

Error:

```text
SyntaxError: Rest parameter must be last formal parameter
```

Correct:

```javascript
function add(...numbers) {
  console.log(numbers);
}
```

Do not add a comma after a rest parameter.

---

## Error 3: Multiple Rest Parameters

Incorrect:

```javascript
function test(...numbers, ...names) {
  console.log(numbers);
  console.log(names);
}
```

This produces a syntax error.

Correct:

```javascript
function test(type, ...values) {
  console.log(type);
  console.log(values);
}
```

---

## Error 4: Forgetting the Three Dots

Incorrect:

```javascript
function add(numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, 20, 30));
```

Here, `numbers` receives only the first value:

```text
10
```

JavaScript tries to run:

```javascript
10.reduce()
```

Error:

```text
TypeError: numbers.reduce is not a function
```

Correct:

```javascript
function add(...numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, 20, 30));
```

Output:

```text
60
```

---

## Error 5: Passing an Array Without Spread

```javascript
function add(...numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

const values = [10, 20, 30];

console.log(add(values));
```

Here, `numbers` becomes:

```javascript
[[10, 20, 30]]
```

The function receives one complete array as one argument.

Correct:

```javascript
console.log(add(...values));
```

Output:

```text
60
```

The spread operator sends every array item separately.

---

## Error 6: Passing Strings Instead of Numbers

```javascript
function add(...numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, "20", 30));
```

Output:

```text
102030
```

Why?

First:

```javascript
0 + 10
```

Result:

```text
10
```

Then:

```javascript
10 + "20"
```

Result:

```text
"1020"
```

Then:

```javascript
"1020" + 30
```

Result:

```text
"102030"
```

JavaScript joins the values as strings.

Safer version:

```javascript
function add(...numbers) {
  const allAreNumbers = numbers.every((number) => {
    return typeof number === "number";
  });

  if (!allAreNumbers) {
    throw new TypeError(
      "All values must be numbers"
    );
  }

  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, 20, 30));
```

Output:

```text
60
```

Calling:

```javascript
add(10, "20", 30);
```

Error:

```text
TypeError: All values must be numbers
```

---

## Error 7: Empty Rest Array

```javascript
function findLargest(...numbers) {
  return Math.max(...numbers);
}

console.log(findLargest());
```

Output:

```text
-Infinity
```

This happens because no value was provided.

Safer version:

```javascript
function findLargest(...numbers) {
  if (numbers.length === 0) {
    return "Please provide at least one number";
  }

  return Math.max(...numbers);
}

console.log(findLargest());
```

Output:

```text
Please provide at least one number
```

---

## Error 8: `NaN` Values

```javascript
function add(...numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, NaN, 20));
```

Output:

```text
NaN
```

Safer version:

```javascript
function add(...numbers) {
  const validNumbers = numbers.every((number) => {
    return Number.isFinite(number);
  });

  if (!validNumbers) {
    return "Please provide valid numbers";
  }

  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

console.log(add(10, 20, 30));
```

Output:

```text
60
```

---

# Practical Student Report Example

```javascript
function generateStudentReport(
  studentName,
  ...marks
) {
  if (marks.length === 0) {
    return "No marks provided";
  }

  const allAreNumbers = marks.every((mark) => {
    return typeof mark === "number";
  });

  if (!allAreNumbers) {
    return "All marks must be numbers";
  }

  const total = marks.reduce((sum, mark) => {
    return sum + mark;
  }, 0);

  const average = total / marks.length;

  return {
    studentName: studentName,
    marks: marks,
    total: total,
    average: average
  };
}

console.log(
  generateStudentReport(
    "Niket",
    80,
    75,
    90,
    85
  )
);
```

Output:

```javascript
{
  studentName: "Niket",
  marks: [80, 75, 90, 85],
  total: 330,
  average: 82.5
}
```

---

# Practical Product Price Example

```javascript
function calculateProductTotal(
  productName,
  ...prices
) {
  if (prices.length === 0) {
    return "No prices provided";
  }

  const total = prices.reduce((sum, price) => {
    return sum + price;
  }, 0);

  return {
    productName: productName,
    prices: prices,
    totalPrice: total
  };
}

console.log(
  calculateProductTotal(
    "Laptop Accessories",
    500,
    1000,
    250,
    750
  )
);
```

Output:

```javascript
{
  productName: "Laptop Accessories",
  prices: [500, 1000, 250, 750],
  totalPrice: 2500
}
```

---

# Important Rules

1. Rest parameters use three dots:

```javascript
...values
```

2. Rest parameters collect multiple arguments into one array.

3. The rest parameter must always be the last parameter.

4. Only one rest parameter can be used in one parameter list.

5. Rest parameters create a real JavaScript array.

6. Array methods can be used directly with rest parameters.

7. Rest parameters work with normal functions and arrow functions.

8. Rest collects values.

9. Spread expands values.

---

# Rest vs Spread Summary

## Rest

```javascript
function show(...values) {
  console.log(values);
}
```

Meaning:

```text
Multiple values → One array
```

## Spread

```javascript
const values = [10, 20, 30];

console.log(...values);
```

Meaning:

```text
One array → Multiple values
```

---

# Final Example

```javascript
function introduce(name, age, ...skills) {
  console.log(`Name: ${name}`);
  console.log(`Age: ${age}`);
  console.log(
    `Skills: ${skills.join(", ")}`
  );
}

introduce(
  "Niket",
  21,
  "JavaScript",
  "Node.js",
  "MongoDB"
);
```

Output:

```text
Name: Niket
Age: 21
Skills: JavaScript, Node.js, MongoDB
```

---

# Final Definition

A rest parameter is used when a function needs to accept an unknown or unlimited number of arguments.

It collects all remaining arguments into one array.

Syntax:

```javascript
function example(...values) {
  console.log(values);
}
```
