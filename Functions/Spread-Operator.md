# JavaScript Spread Operator

## What is the Spread Operator?

The spread operator is written using three dots:

```javascript
...
```

The spread operator is used to expand values from:

* Arrays
* Objects
* Strings

It takes values from one place and spreads them into another place.

---

## Simple Example

```javascript
const numbers = [10, 20, 30];

console.log(...numbers);
```

Output:

```text
10 20 30
```

Without spread:

```javascript
console.log(numbers);
```

Output:

```text
[10, 20, 30]
```

With spread:

```javascript
console.log(...numbers);
```

Output:

```text
10 20 30
```

The array values are expanded individually.

---

# Spread Operator with Arrays

## 1. Copy an Array

The spread operator can create a new copy of an array.

```javascript
const originalArray = [10, 20, 30];

const copiedArray = [...originalArray];

console.log(copiedArray);
```

Output:

```text
[10, 20, 30]
```

Now both arrays are different arrays.

```javascript
const originalArray = [10, 20, 30];

const copiedArray = [...originalArray];

copiedArray.push(40);

console.log(originalArray);
console.log(copiedArray);
```

Output:

```text
[10, 20, 30]
[10, 20, 30, 40]
```

Changing `copiedArray` does not change `originalArray`.

---

## Without Spread Operator

```javascript
const originalArray = [10, 20, 30];

const copiedArray = originalArray;

copiedArray.push(40);

console.log(originalArray);
console.log(copiedArray);
```

Output:

```text
[10, 20, 30, 40]
[10, 20, 30, 40]
```

Both variables point to the same array.

---

## 2. Merge Arrays

The spread operator can combine multiple arrays.

```javascript
const frontend = ["HTML", "CSS", "JavaScript"];
const backend = ["Node.js", "Express.js", "MongoDB"];

const technologies = [...frontend, ...backend];

console.log(technologies);
```

Output:

```text
[
  "HTML",
  "CSS",
  "JavaScript",
  "Node.js",
  "Express.js",
  "MongoDB"
]
```

You can also add extra values.

```javascript
const frontend = ["HTML", "CSS"];
const backend = ["Node.js", "MongoDB"];

const technologies = [
  "Git",
  ...frontend,
  "React",
  ...backend,
  "Docker"
];

console.log(technologies);
```

Output:

```text
[
  "Git",
  "HTML",
  "CSS",
  "React",
  "Node.js",
  "MongoDB",
  "Docker"
]
```

---

## 3. Add Elements to an Array

### Add at the Beginning

```javascript
const numbers = [20, 30, 40];

const updatedNumbers = [10, ...numbers];

console.log(updatedNumbers);
```

Output:

```text
[10, 20, 30, 40]
```

### Add at the End

```javascript
const numbers = [10, 20, 30];

const updatedNumbers = [...numbers, 40];

console.log(updatedNumbers);
```

Output:

```text
[10, 20, 30, 40]
```

### Add in the Middle

```javascript
const firstPart = [10, 20];
const secondPart = [40, 50];

const numbers = [...firstPart, 30, ...secondPart];

console.log(numbers);
```

Output:

```text
[10, 20, 30, 40, 50]
```

---

## 4. Pass Array Values to a Function

Suppose a function requires separate arguments.

```javascript
function add(a, b, c) {
  return a + b + c;
}

const numbers = [10, 20, 30];

console.log(add(...numbers));
```

Output:

```text
60
```

This code:

```javascript
add(...numbers);
```

works like:

```javascript
add(10, 20, 30);
```

---

## Without Spread

```javascript
function add(a, b, c) {
  return a + b + c;
}

const numbers = [10, 20, 30];

console.log(add(numbers));
```

The complete array is passed into `a`.

```text
a = [10, 20, 30]
b = undefined
c = undefined
```

---

## 5. Use Spread with Math Methods

The `Math.max()` method expects separate numbers.

```javascript
console.log(Math.max(10, 50, 20, 80));
```

Output:

```text
80
```

When numbers are inside an array:

```javascript
const numbers = [10, 50, 20, 80];

console.log(Math.max(...numbers));
```

Output:

```text
80
```

### Find Minimum Value

```javascript
const numbers = [10, 50, 20, 5, 80];

console.log(Math.min(...numbers));
```

Output:

```text
5
```

### Without Spread

```javascript
const numbers = [10, 50, 20, 80];

console.log(Math.max(numbers));
```

Output:

```text
NaN
```

`Math.max()` cannot directly process an array.

---

## 6. Remove Duplicate Array Values

Spread is often used with `Set`.

```javascript
const numbers = [10, 20, 10, 30, 20, 40];

const uniqueNumbers = [...new Set(numbers)];

console.log(uniqueNumbers);
```

Output:

```text
[10, 20, 30, 40]
```

Explanation:

```javascript
new Set(numbers);
```

removes duplicate values.

Then:

```javascript
[...new Set(numbers)];
```

converts the `Set` back into an array.

---

# Spread Operator with Strings

A string can be expanded into individual characters.

```javascript
const name = "Niket";

const characters = [...name];

console.log(characters);
```

Output:

```text
["N", "i", "k", "e", "t"]
```

You can also spread a string directly.

```javascript
console.log(..."Hello");
```

Output:

```text
H e l l o
```

---

## Reverse a String Using Spread

```javascript
const text = "JavaScript";

const reversedText = [...text].reverse().join("");

console.log(reversedText);
```

Output:

```text
tpircSavaJ
```

Explanation:

```javascript
[...text]
```

converts the string into an array of characters.

```javascript
.reverse()
```

reverses the array.

```javascript
.join("")
```

joins the characters back into a string.

---

# Spread Operator with Objects

## 1. Copy an Object

The spread operator can create a copy of an object.

```javascript
const user = {
  name: "Niket",
  age: 22
};

const copiedUser = {
  ...user
};

console.log(copiedUser);
```

Output:

```text
{
  name: "Niket",
  age: 22
}
```

Changing a top-level property in the copied object does not change the original object.

```javascript
const user = {
  name: "Niket",
  age: 22
};

const copiedUser = {
  ...user
};

copiedUser.age = 23;

console.log(user);
console.log(copiedUser);
```

Output:

```text
{ name: "Niket", age: 22 }

{ name: "Niket", age: 23 }
```

---

## 2. Update an Object

You can copy an object and update one property.

```javascript
const user = {
  name: "Niket",
  age: 22,
  city: "Ahmedabad"
};

const updatedUser = {
  ...user,
  age: 23
};

console.log(updatedUser);
```

Output:

```text
{
  name: "Niket",
  age: 23,
  city: "Ahmedabad"
}
```

The original object remains unchanged.

```javascript
console.log(user);
```

Output:

```text
{
  name: "Niket",
  age: 22,
  city: "Ahmedabad"
}
```

---

## Property Order is Important

When the same property appears multiple times, the last value is used.

```javascript
const user = {
  name: "Niket",
  age: 22
};

const updatedUser = {
  ...user,
  age: 25
};

console.log(updatedUser);
```

Output:

```text
{
  name: "Niket",
  age: 25
}
```

Here, `age: 25` comes after `...user`, so it replaces the old value.

---

## Incorrect Property Order

```javascript
const user = {
  name: "Niket",
  age: 22
};

const updatedUser = {
  age: 25,
  ...user
};

console.log(updatedUser);
```

Output:

```text
{
  age: 22,
  name: "Niket"
}
```

The value `age: 25` is replaced because `...user` comes after it.

Correct order:

```javascript
const updatedUser = {
  ...user,
  age: 25
};
```

---

## 3. Add a New Property

```javascript
const user = {
  name: "Niket",
  age: 22
};

const updatedUser = {
  ...user,
  city: "Ahmedabad"
};

console.log(updatedUser);
```

Output:

```text
{
  name: "Niket",
  age: 22,
  city: "Ahmedabad"
}
```

---

## 4. Merge Objects

```javascript
const personalDetails = {
  name: "Niket",
  age: 22
};

const professionalDetails = {
  role: "Developer",
  skill: "JavaScript"
};

const user = {
  ...personalDetails,
  ...professionalDetails
};

console.log(user);
```

Output:

```text
{
  name: "Niket",
  age: 22,
  role: "Developer",
  skill: "JavaScript"
}
```

---

## Duplicate Properties While Merging

```javascript
const object1 = {
  name: "Niket",
  city: "Ahmedabad"
};

const object2 = {
  role: "Developer",
  city: "Rajkot"
};

const result = {
  ...object1,
  ...object2
};

console.log(result);
```

Output:

```text
{
  name: "Niket",
  city: "Rajkot",
  role: "Developer"
}
```

`object2.city` replaces `object1.city` because `object2` is spread later.

---

# Shallow Copy Problem

The spread operator creates a shallow copy, not a deep copy.

Example:

```javascript
const user = {
  name: "Niket",
  address: {
    city: "Ahmedabad",
    state: "Gujarat"
  }
};

const copiedUser = {
  ...user
};

copiedUser.name = "Rahul";
copiedUser.address.city = "Rajkot";

console.log(user);
console.log(copiedUser);
```

Output:

```text
{
  name: "Niket",
  address: {
    city: "Rajkot",
    state: "Gujarat"
  }
}
```

```text
{
  name: "Rahul",
  address: {
    city: "Rajkot",
    state: "Gujarat"
  }
}
```

The top-level property `name` is copied separately.

However, the nested `address` object is still shared.

---

## Correct Way to Copy a Nested Object

```javascript
const user = {
  name: "Niket",
  address: {
    city: "Ahmedabad",
    state: "Gujarat"
  }
};

const copiedUser = {
  ...user,
  address: {
    ...user.address
  }
};

copiedUser.address.city = "Rajkot";

console.log(user.address.city);
console.log(copiedUser.address.city);
```

Output:

```text
Ahmedabad
Rajkot
```

Now the nested `address` object is also copied.

---

# Copy a Nested Array

```javascript
const original = [
  [10, 20],
  [30, 40]
];

const copied = [...original];

copied[0][0] = 100;

console.log(original);
```

Output:

```text
[
  [100, 20],
  [30, 40]
]
```

The nested arrays are still shared.

Correct way:

```javascript
const original = [
  [10, 20],
  [30, 40]
];

const copied = original.map((array) => [...array]);

copied[0][0] = 100;

console.log(original);
console.log(copied);
```

Output:

```text
[
  [10, 20],
  [30, 40]
]
```

```text
[
  [100, 20],
  [30, 40]
]
```

---

# Spread Operator vs Rest Parameter

Both spread and rest use three dots:

```javascript
...
```

But their work is different.

---

## Spread Operator

Spread expands values.

```javascript
const numbers = [10, 20, 30];

console.log(...numbers);
```

Output:

```text
10 20 30
```

Think:

```text
Spread = Expand values
```

---

## Rest Parameter

Rest collects multiple values into one array.

```javascript
function showNumbers(...numbers) {
  console.log(numbers);
}

showNumbers(10, 20, 30);
```

Output:

```text
[10, 20, 30]
```

Think:

```text
Rest = Collect values
```

---

## Spread and Rest in One Example

```javascript
function add(...numbers) {
  return numbers.reduce((total, number) => {
    return total + number;
  }, 0);
}

const values = [10, 20, 30];

console.log(add(...values));
```

Output:

```text
60
```

Here:

```javascript
...values
```

is spread because it expands the array.

```javascript
...numbers
```

is rest because it collects the arguments into an array.

---

# Common Spread Operator Errors

## Error 1: Spreading a Number into an Array

Incorrect:

```javascript
const number = 100;

const result = [...number];
```

Error:

```text
TypeError: number is not iterable
```

A number is not iterable.

Correct examples:

```javascript
const result1 = [...[100]];
const result2 = [..."100"];

console.log(result1);
console.log(result2);
```

Output:

```text
[100]

["1", "0", "0"]
```

---

## Error 2: Spreading `null` into an Array

Incorrect:

```javascript
const value = null;

const result = [...value];
```

Error:

```text
TypeError: value is not iterable
```

Correct:

```javascript
const value = null;

const result = [...(value || [])];

console.log(result);
```

Output:

```text
[]
```

---

## Error 3: Spreading `undefined` into an Array

Incorrect:

```javascript
const value = undefined;

const result = [...value];
```

Error:

```text
TypeError: value is not iterable
```

Correct:

```javascript
const value = undefined;

const result = [...(value || [])];

console.log(result);
```

Output:

```text
[]
```

---

## Error 4: Wrong Object Update Order

```javascript
const user = {
  name: "Niket",
  age: 22
};

const updatedUser = {
  age: 30,
  ...user
};

console.log(updatedUser.age);
```

Output:

```text
22
```

This is not a syntax error, but it is a logical error.

Correct:

```javascript
const updatedUser = {
  ...user,
  age: 30
};

console.log(updatedUser.age);
```

Output:

```text
30
```

---

## Error 5: Expecting a Deep Copy

```javascript
const user = {
  name: "Niket",
  address: {
    city: "Ahmedabad"
  }
};

const copiedUser = {
  ...user
};

copiedUser.address.city = "Surat";

console.log(user.address.city);
```

Output:

```text
Surat
```

Many beginners expect the result to remain `"Ahmedabad"`.

Spread only creates a shallow copy.

Correct:

```javascript
const copiedUser = {
  ...user,
  address: {
    ...user.address
  }
};
```

---

## Error 6: Using Spread in an Invalid Position

Incorrect:

```javascript
const numbers = [10, 20, 30];

const result = ...numbers;
```

Error:

```text
SyntaxError: Unexpected token '...'
```

Correct:

```javascript
const result = [...numbers];
```

You can also use it like this:

```javascript
console.log(...numbers);
```

Or:

```javascript
function add(a, b, c) {
  return a + b + c;
}

add(...numbers);
```

---

## Error 7: Too Many Function Arguments

Spreading a very large array into a function can cause an error.

```javascript
const numbers = new Array(1000000).fill(1);

Math.max(...numbers);
```

Possible error:

```text
RangeError: Maximum call stack size exceeded
```

A safer method for very large arrays is `reduce()`.

```javascript
const numbers = new Array(1000000).fill(1);

const maximum = numbers.reduce((max, number) => {
  return number > max ? number : max;
}, -Infinity);

console.log(maximum);
```

---

# Practical Example

Suppose you have product information.

```javascript
const product = {
  name: "Laptop",
  price: 50000,
  stock: 10
};
```

You want to update the price and add a discount without changing the original object.

```javascript
const updatedProduct = {
  ...product,
  price: 45000,
  discount: "10%"
};

console.log(product);
console.log(updatedProduct);
```

Output:

```text
{
  name: "Laptop",
  price: 50000,
  stock: 10
}
```

```text
{
  name: "Laptop",
  price: 45000,
  stock: 10,
  discount: "10%"
}
```

The original product object is not changed.

---

# Important Points

* The spread operator is written as `...`.
* It expands values.
* It works with arrays, strings and objects.
* It can copy arrays and objects.
* It can merge arrays and objects.
* It can add new values.
* It can update object properties.
* It can pass array values as function arguments.
* It creates a shallow copy, not a deep copy.
* Property order is important when merging objects.
* Numbers cannot be spread into arrays.
* `null` and `undefined` cannot be spread into arrays.
* Spread expands values.
* Rest collects values.

---

# Final Example

```javascript
const frontend = ["HTML", "CSS", "JavaScript"];
const backend = ["Node.js", "Express.js", "MongoDB"];

const allSkills = [...frontend, ...backend];

const user = {
  name: "Niket",
  age: 22
};

const updatedUser = {
  ...user,
  age: 23,
  skills: allSkills
};

console.log(updatedUser);
```

Output:

```text
{
  name: "Niket",
  age: 23,
  skills: [
    "HTML",
    "CSS",
    "JavaScript",
    "Node.js",
    "Express.js",
    "MongoDB"
  ]
}
```

---

# Conclusion

The spread operator is one of the most useful features in modern JavaScript.

It makes it easy to:

* Copy arrays
* Copy objects
* Merge arrays
* Merge objects
* Update object properties
* Add array values
* Pass values to functions
* Convert strings into characters

Always remember:

```text
Spread Operator = Expand values
Rest Parameter = Collect values
```
