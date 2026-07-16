# Recursion in JavaScript

## What is Recursion?

Recursion means a function calls itself to solve a problem.

A recursive function continues calling itself until a stopping condition becomes true.

Example:

```javascript
function hello() {
  console.log("Hello");

  hello();
}

hello();
```

This function keeps calling itself forever because it does not have a stopping condition.

JavaScript will eventually show this error:

```text
RangeError: Maximum call stack size exceeded
```

Every recursive function must have a stopping condition.

---

# Important Parts of Recursion

A recursive function normally contains two important parts:

1. Base case
2. Recursive case

---

## 1. Base Case

The base case is the condition that stops the function.

Example:

```javascript
if (number === 0) {
  return;
}
```

When `number` becomes `0`, the function stops.

---

## 2. Recursive Case

The recursive case is where the function calls itself.

Example:

```javascript
countDown(number - 1);
```

Complete example:

```javascript
function countDown(number) {
  if (number === 0) {
    console.log("Finished");
    return;
  }

  console.log(number);

  countDown(number - 1);
}

countDown(5);
```

Output:

```text
5
4
3
2
1
Finished
```

---

# How Recursion Works

Consider this function call:

```javascript
countDown(3);
```

The function calls happen like this:

```text
countDown(3)
    ↓
countDown(2)
    ↓
countDown(1)
    ↓
countDown(0)
    ↓
Stop
```

Detailed flow:

```text
countDown(3) prints 3
countDown(2) prints 2
countDown(1) prints 1
countDown(0) stops
```

---

# Example 1: Print Numbers from 1 to 5

```javascript
function printNumbers(number) {
  if (number > 5) {
    return;
  }

  console.log(number);

  printNumbers(number + 1);
}

printNumbers(1);
```

Output:

```text
1
2
3
4
5
```

Flow:

```text
printNumbers(1)
printNumbers(2)
printNumbers(3)
printNumbers(4)
printNumbers(5)
printNumbers(6) → Stop
```

---

# Example 2: Print Numbers from 5 to 1

```javascript
function reverseCount(number) {
  if (number === 0) {
    return;
  }

  console.log(number);

  reverseCount(number - 1);
}

reverseCount(5);
```

Output:

```text
5
4
3
2
1
```

---

# Example 3: Find the Sum of Numbers

Suppose we want to calculate:

```text
1 + 2 + 3 + 4 + 5
```

Using recursion:

```javascript
function sum(number) {
  if (number === 1) {
    return 1;
  }

  return number + sum(number - 1);
}

console.log(sum(5));
```

Output:

```text
15
```

How it works:

```text
sum(5)
= 5 + sum(4)

= 5 + 4 + sum(3)

= 5 + 4 + 3 + sum(2)

= 5 + 4 + 3 + 2 + sum(1)

= 5 + 4 + 3 + 2 + 1

= 15
```

---

# Example 4: Factorial Using Recursion

Factorial means multiplying a number by all positive numbers below it.

Example:

```text
5! = 5 × 4 × 3 × 2 × 1
```

Result:

```text
120
```

JavaScript code:

```javascript
function factorial(number) {
  if (number === 0 || number === 1) {
    return 1;
  }

  return number * factorial(number - 1);
}

console.log(factorial(5));
```

Output:

```text
120
```

How it works:

```text
factorial(5)
= 5 × factorial(4)

= 5 × 4 × factorial(3)

= 5 × 4 × 3 × factorial(2)

= 5 × 4 × 3 × 2 × factorial(1)

= 5 × 4 × 3 × 2 × 1

= 120
```

---

# Example 5: Fibonacci Series Using Recursion

The Fibonacci series is:

```text
0, 1, 1, 2, 3, 5, 8, 13...
```

Every number is the sum of the previous two numbers.

```javascript
function fibonacci(number) {
  if (number === 0) {
    return 0;
  }

  if (number === 1) {
    return 1;
  }

  return fibonacci(number - 1) + fibonacci(number - 2);
}

console.log(fibonacci(6));
```

Output:

```text
8
```

The Fibonacci positions are:

```text
Position: 0  1  2  3  4  5  6
Value:    0  1  1  2  3  5  8
```

Print the Fibonacci series:

```javascript
function fibonacci(number) {
  if (number === 0) {
    return 0;
  }

  if (number === 1) {
    return 1;
  }

  return fibonacci(number - 1) + fibonacci(number - 2);
}

for (let i = 0; i <= 8; i++) {
  console.log(fibonacci(i));
}
```

Output:

```text
0
1
1
2
3
5
8
13
21
```

This solution becomes slow for large numbers because it repeats the same calculations many times.

---

# Example 6: Reverse a String

```javascript
function reverseString(text) {
  if (text === "") {
    return "";
  }

  return reverseString(text.slice(1)) + text[0];
}

console.log(reverseString("hello"));
```

Output:

```text
olleh
```

How it works:

```text
reverseString("hello")

reverseString("ello") + "h"

reverseString("llo") + "e" + "h"

reverseString("lo") + "l" + "e" + "h"

reverseString("o") + "l" + "l" + "e" + "h"

reverseString("") + "o" + "l" + "l" + "e" + "h"

"olleh"
```

---

# Example 7: Find the Power of a Number

Example:

```text
2³ = 2 × 2 × 2
```

Result:

```text
8
```

Using recursion:

```javascript
function power(base, exponent) {
  if (exponent === 0) {
    return 1;
  }

  return base * power(base, exponent - 1);
}

console.log(power(2, 3));
```

Output:

```text
8
```

How it works:

```text
power(2, 3)
= 2 × power(2, 2)

= 2 × 2 × power(2, 1)

= 2 × 2 × 2 × power(2, 0)

= 2 × 2 × 2 × 1

= 8
```

---

# Example 8: Find the Sum of Array Elements

```javascript
function arraySum(array, index = 0) {
  if (index === array.length) {
    return 0;
  }

  return array[index] + arraySum(array, index + 1);
}

const numbers = [10, 20, 30, 40];

console.log(arraySum(numbers));
```

Output:

```text
100
```

How it works:

```text
10 + 20 + 30 + 40 = 100
```

---

# Example 9: Find the Maximum Number in an Array

```javascript
function findMaximum(array, index = 0) {
  if (index === array.length - 1) {
    return array[index];
  }

  const maximumFromRemainingItems = findMaximum(
    array,
    index + 1
  );

  return Math.max(
    array[index],
    maximumFromRemainingItems
  );
}

const numbers = [10, 50, 20, 80, 30];

console.log(findMaximum(numbers));
```

Output:

```text
80
```

---

# Example 10: Check a Palindrome

A palindrome is a word that reads the same forward and backward.

Examples:

```text
madam
level
racecar
```

JavaScript code:

```javascript
function isPalindrome(text) {
  if (text.length <= 1) {
    return true;
  }

  if (text[0] !== text[text.length - 1]) {
    return false;
  }

  return isPalindrome(text.slice(1, -1));
}

console.log(isPalindrome("madam"));
console.log(isPalindrome("hello"));
```

Output:

```text
true
false
```

---

# Recursion and the Call Stack

JavaScript uses the call stack to remember function calls.

Example:

```javascript
function test(number) {
  if (number === 0) {
    return;
  }

  console.log(number);

  test(number - 1);
}

test(3);
```

Function calls are stored like this:

```text
test(3)
test(2)
test(1)
test(0)
```

When the base case is reached, the functions finish in reverse order:

```text
test(0) finishes
test(1) finishes
test(2) finishes
test(3) finishes
```

This process is called stack unwinding.

---

# Code Before and After the Recursive Call

```javascript
function show(number) {
  if (number === 0) {
    return;
  }

  console.log("Before:", number);

  show(number - 1);

  console.log("After:", number);
}

show(3);
```

Output:

```text
Before: 3
Before: 2
Before: 1
After: 1
After: 2
After: 3
```

The code before the recursive call runs immediately:

```javascript
console.log("Before:", number);
```

The code after the recursive call waits until the deeper function finishes:

```javascript
console.log("After:", number);
```

Flow:

```text
Before 3
    Before 2
        Before 1
        After 1
    After 2
After 3
```

---

# Recursion vs Loop

The same problem can often be solved using recursion or a loop.

## Using a Loop

```javascript
for (let i = 5; i >= 1; i--) {
  console.log(i);
}
```

## Using Recursion

```javascript
function countDown(number) {
  if (number === 0) {
    return;
  }

  console.log(number);

  countDown(number - 1);
}

countDown(5);
```

Both produce:

```text
5
4
3
2
1
```

## Difference Between Recursion and Loop

| Recursion                  | Loop                            |
| -------------------------- | ------------------------------- |
| Function calls itself      | Code repeats using a loop       |
| Uses the call stack        | Usually uses less memory        |
| Needs a base case          | Needs a loop condition          |
| Useful for nested problems | Useful for simple repetition    |
| Can cause stack overflow   | Can cause an infinite loop      |
| Sometimes easier to read   | Usually faster for simple tasks |

---

# Common Recursion Errors

## Error 1: Missing Base Case

Wrong code:

```javascript
function count(number) {
  console.log(number);

  count(number - 1);
}

count(5);
```

This function never stops.

Error:

```text
RangeError: Maximum call stack size exceeded
```

Correct code:

```javascript
function count(number) {
  if (number === 0) {
    return;
  }

  console.log(number);

  count(number - 1);
}

count(5);
```

---

## Error 2: Base Case Is Never Reached

Wrong code:

```javascript
function count(number) {
  if (number === 0) {
    return;
  }

  console.log(number);

  count(number + 1);
}

count(5);
```

The values become:

```text
5
6
7
8
9
...
```

The number never becomes `0`.

Correct code:

```javascript
function count(number) {
  if (number === 0) {
    return;
  }

  console.log(number);

  count(number - 1);
}

count(5);
```

---

## Error 3: Incorrect Base Case

Wrong factorial code:

```javascript
function factorial(number) {
  if (number === 0) {
    return 0;
  }

  return number * factorial(number - 1);
}

console.log(factorial(5));
```

Output:

```text
0
```

Why?

```text
5 × 4 × 3 × 2 × 1 × 0 = 0
```

Correct code:

```javascript
function factorial(number) {
  if (number === 0) {
    return 1;
  }

  return number * factorial(number - 1);
}

console.log(factorial(5));
```

Output:

```text
120
```

---

## Error 4: Forgetting `return`

Wrong code:

```javascript
function sum(number) {
  if (number === 1) {
    return 1;
  }

  number + sum(number - 1);
}

console.log(sum(5));
```

Output:

```text
undefined
```

Correct code:

```javascript
function sum(number) {
  if (number === 1) {
    return 1;
  }

  return number + sum(number - 1);
}

console.log(sum(5));
```

Output:

```text
15
```

---

## Error 5: Negative Number Problem

Wrong code:

```javascript
function factorial(number) {
  if (number === 0) {
    return 1;
  }

  return number * factorial(number - 1);
}

console.log(factorial(-5));
```

The numbers become:

```text
-5
-6
-7
-8
...
```

The base case is never reached.

Correct code:

```javascript
function factorial(number) {
  if (number < 0) {
    return "Factorial is not available for negative numbers";
  }

  if (number === 0 || number === 1) {
    return 1;
  }

  return number * factorial(number - 1);
}

console.log(factorial(-5));
```

Output:

```text
Factorial is not available for negative numbers
```

---

## Error 6: Wrong Data Type

```javascript
function factorial(number) {
  if (typeof number !== "number") {
    return "Please provide a number";
  }

  if (number < 0) {
    return "Number cannot be negative";
  }

  if (number === 0 || number === 1) {
    return 1;
  }

  return number * factorial(number - 1);
}

console.log(factorial("5"));
```

Output:

```text
Please provide a number
```

---

## Error 7: Decimal Number

Factorial normally works with whole numbers.

```javascript
function factorial(number) {
  if (!Number.isInteger(number)) {
    return "Please provide a whole number";
  }

  if (number < 0) {
    return "Number cannot be negative";
  }

  if (number === 0 || number === 1) {
    return 1;
  }

  return number * factorial(number - 1);
}

console.log(factorial(5.5));
```

Output:

```text
Please provide a whole number
```

---

## Error 8: Too Many Recursive Calls

Even correct recursive code can fail when the input is very large.

```javascript
function countDown(number) {
  if (number === 0) {
    return;
  }

  countDown(number - 1);
}

countDown(100000);
```

Possible error:

```text
RangeError: Maximum call stack size exceeded
```

For very large repetition, using a loop is safer.

```javascript
for (let i = 100000; i >= 0; i--) {
  // Code here
}
```

---

# Safe Factorial Function

```javascript
function factorial(number) {
  if (typeof number !== "number") {
    throw new TypeError("Input must be a number");
  }

  if (!Number.isInteger(number)) {
    throw new Error("Input must be a whole number");
  }

  if (number < 0) {
    throw new RangeError("Input cannot be negative");
  }

  if (number === 0 || number === 1) {
    return 1;
  }

  return number * factorial(number - 1);
}

try {
  console.log(factorial(5));
} catch (error) {
  console.log(error.message);
}
```

Output:

```text
120
```

Invalid input example:

```javascript
try {
  console.log(factorial(-5));
} catch (error) {
  console.log(error.message);
}
```

Output:

```text
Input cannot be negative
```

---

# Nested Object Recursion Example

Recursion is very useful when working with nested objects.

```javascript
const categories = {
  name: "Electronics",
  children: [
    {
      name: "Mobile",
      children: [
        {
          name: "Android",
          children: [],
        },
        {
          name: "iPhone",
          children: [],
        },
      ],
    },
    {
      name: "Laptop",
      children: [],
    },
  ],
};
```

Print every category name:

```javascript
function printCategories(category) {
  console.log(category.name);

  for (const child of category.children) {
    printCategories(child);
  }
}

printCategories(categories);
```

Output:

```text
Electronics
Mobile
Android
iPhone
Laptop
```

Every category can contain more child categories, so recursion is useful here.

---

# When Should We Use Recursion?

Recursion is useful when a problem contains smaller versions of the same problem.

Common uses include:

* Factorial calculations
* Fibonacci series
* Tree traversal
* Folder and file structures
* Nested arrays
* Nested objects
* Graph traversal
* Backtracking problems
* Merge sort
* Quick sort
* Searching nested data

---

# Advantages of Recursion

1. Recursive code can be easier to understand.
2. It is useful for nested data.
3. It is useful for tree and graph problems.
4. Some mathematical problems are naturally recursive.
5. It can reduce the amount of code.

---

# Disadvantages of Recursion

1. It uses more memory.
2. Every function call is stored in the call stack.
3. It can be slower than a loop.
4. A missing base case causes infinite recursion.
5. Large inputs can cause a stack overflow.
6. Recursive code can sometimes be difficult to debug.

---

# Important Rules of Recursion

Always remember these rules:

```text
1. Create a base case.
2. Make sure the input moves toward the base case.
3. Return the recursive result when required.
4. Validate the input.
5. Avoid recursion for extremely large repetition.
```

Basic recursive function structure:

```javascript
function recursiveFunction(value) {
  if (stoppingCondition) {
    return finalValue;
  }

  return recursiveFunction(updatedValue);
}
```

---

# Final Example

```javascript
function countDown(number) {
  if (typeof number !== "number") {
    return "Please enter a number";
  }

  if (!Number.isInteger(number)) {
    return "Please enter a whole number";
  }

  if (number < 0) {
    return "Please enter a positive number";
  }

  if (number === 0) {
    console.log("Completed");
    return;
  }

  console.log(number);

  countDown(number - 1);
}

countDown(5);
```

Output:

```text
5
4
3
2
1
Completed
```

---

# Conclusion

Recursion means a function calls itself to solve a smaller part of the same problem.

Every recursive function should have:

```text
Base Case + Recursive Case
```

The base case stops the function.

The recursive case calls the function again with a smaller or changed value.

Without a correct base case, recursion may cause:

```text
RangeError: Maximum call stack size exceeded
```
