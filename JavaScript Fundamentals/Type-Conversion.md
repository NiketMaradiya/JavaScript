# JavaScript Type Conversion

## What is Type Conversion?

Type Conversion means changing one data type into another data type.

Example:

- String → Number
- Number → String
- Boolean → Number
- Number → Boolean

Example:

```javascript
let age = "20";
```

Here `"20"` is a String.

Convert it into Number.

```javascript
let age = Number("20");

console.log(age);
```

Output

```
20
```

Type

```javascript
console.log(typeof age);
```

Output

```
number
```

---

# Why Do We Need Type Conversion?

Suppose a user enters two numbers.

```javascript
let num1 = "10";
let num2 = "20";

console.log(num1 + num2);
```

Output

```
1020
```

Why?

Because both values are Strings.

Convert them into Numbers.

```javascript
let num1 = Number("10");
let num2 = Number("20");

console.log(num1 + num2);
```

Output

```
30
```

---

# Types of Type Conversion

There are two types.

1. Implicit Type Conversion (Automatic)
2. Explicit Type Conversion (Manual)

---

# 1. Implicit Type Conversion

JavaScript automatically converts one data type into another.

Example

```javascript
console.log("5" + 2);
```

Output

```
52
```

Explanation

```
"5" + "2"

↓

"52"
```

---

Example

```javascript
console.log("5" - 2);
```

Output

```
3
```

Explanation

```
"5"

↓

5

↓

5 - 2

↓

3
```

---

Example

```javascript
console.log("10" * 2);
```

Output

```
20
```

---

Example

```javascript
console.log("20" / 4);
```

Output

```
5
```

---

Example

```javascript
console.log("20" % 3);
```

Output

```
2
```

---

# '+' Operator

The `+` operator works in two ways.

1. Addition
2. String Concatenation

Example

```javascript
console.log(10 + 20);
```

Output

```
30
```

Example

```javascript
console.log("10" + 20);
```

Output

```
1020
```

Example

```javascript
console.log("Hello " + "World");
```

Output

```
Hello World
```

---

# Comparison Conversion

Example

```javascript
console.log("5" == 5);
```

Output

```
true
```

Because `==` converts data types before comparing.

---

Example

```javascript
console.log("5" === 5);
```

Output

```
false
```

Because `===` checks both value and type.

---

# 2. Explicit Type Conversion

You manually convert data types.

JavaScript provides these methods.

- Number()
- String()
- Boolean()
- parseInt()
- parseFloat()

---

# Number()

Converts a value into Number.

Example

```javascript
Number("100")
```

Output

```
100
```

Example

```javascript
Number("50.5")
```

Output

```
50.5
```

Example

```javascript
Number(true)
```

Output

```
1
```

Example

```javascript
Number(false)
```

Output

```
0
```

Example

```javascript
Number("")
```

Output

```
0
```

Example

```javascript
Number("Hello")
```

Output

```
NaN
```

Example

```javascript
Number(null)
```

Output

```
0
```

Example

```javascript
Number(undefined)
```

Output

```
NaN
```

---

# String()

Converts a value into String.

Example

```javascript
String(100)
```

Output

```
"100"
```

Example

```javascript
String(true)
```

Output

```
"true"
```

Example

```javascript
String(false)
```

Output

```
"false"
```

Example

```javascript
String(null)
```

Output

```
"null"
```

Example

```javascript
String(undefined)
```

Output

```
"undefined"
```

---

# Boolean()

Converts a value into Boolean.

Example

```javascript
Boolean(1)
```

Output

```
true
```

Example

```javascript
Boolean(0)
```

Output

```
false
```

Example

```javascript
Boolean("")
```

Output

```
false
```

Example

```javascript
Boolean("Hello")
```

Output

```
true
```

Example

```javascript
Boolean(null)
```

Output

```
false
```

Example

```javascript
Boolean(undefined)
```

Output

```
false
```

Example

```javascript
Boolean([])
```

Output

```
true
```

Example

```javascript
Boolean({})
```

Output

```
true
```

---

# parseInt()

Converts a String into Integer.

Example

```javascript
parseInt("100")
```

Output

```
100
```

Example

```javascript
parseInt("100px")
```

Output

```
100
```

Example

```javascript
parseInt("10.99")
```

Output

```
10
```

Example

```javascript
parseInt("abc100")
```

Output

```
NaN
```

---

# parseFloat()

Converts a String into Decimal Number.

Example

```javascript
parseFloat("10.99")
```

Output

```
10.99
```

Example

```javascript
parseFloat("100.50px")
```

Output

```
100.5
```

---

# Number() vs parseInt()

```javascript
Number("100px")
```

Output

```
NaN
```

```javascript
parseInt("100px")
```

Output

```
100
```

Difference

- `Number()` converts the complete string.
- `parseInt()` reads numbers until it finds a non-number character.

---

# Common Conversion Table

| Value | Number() | String() | Boolean() |
|--------|----------|----------|-----------|
| `"100"` | `100` | `"100"` | `true` |
| `""` | `0` | `""` | `false` |
| `"Hello"` | `NaN` | `"Hello"` | `true` |
| `true` | `1` | `"true"` | `true` |
| `false` | `0` | `"false"` | `false` |
| `null` | `0` | `"null"` | `false` |
| `undefined` | `NaN` | `"undefined"` | `false` |
| `0` | `0` | `"0"` | `false` |
| `1` | `1` | `"1"` | `true` |
| `[]` | `0` | `""` | `true` |
| `{}` | `NaN` | `"[object Object]"` | `true` |

---

# Real-Life Example

Suppose a user enters age from an HTML form.

```javascript
let age = "25";

console.log(age + 5);
```

Output

```
255
```

Correct way

```javascript
let age = Number("25");

console.log(age + 5);
```

Output

```
30
```

---

# Important Points

- Type Conversion changes one data type into another.
- JavaScript performs Implicit Conversion automatically.
- Explicit Conversion is done using functions.
- `Number()` converts to Number.
- `String()` converts to String.
- `Boolean()` converts to Boolean.
- `parseInt()` converts to Integer.
- `parseFloat()` converts to Decimal Number.
- `==` performs type conversion.
- `===` does not perform type conversion.
- Empty string (`""`), `0`, `null`, `undefined`, and `NaN` are falsy values.

---

# Interview Questions

### 1. What is Type Conversion?

### 2. What is the difference between Implicit and Explicit Type Conversion?

### 3. What is the difference between `==` and `===`?

### 4. What is `NaN`?

### 5. What is the difference between `Number()` and `parseInt()`?

### 6. What is the output?

```javascript
console.log("5" + 2);
```

### 7. What is the output?

```javascript
console.log("5" - 2);
```

### 8. What is the output?

```javascript
console.log(Number(""));
```

### 9. What is the output?

```javascript
console.log(Boolean([]));
```

### 10. What is the output?

```javascript
console.log("5" == 5);
console.log("5" === 5);
```

### 11. What is the output?

```javascript
console.log(Number(null));
console.log(Number(undefined));
```

### 12. What is the output?

```javascript
console.log(parseInt("100px"));
console.log(Number("100px"));
```

---

# Summary

- Type Conversion means changing one data type into another.
- There are two types: Implicit and Explicit.
- `Number()`, `String()`, `Boolean()`, `parseInt()`, and `parseFloat()` are the main conversion methods.
- Use `===` instead of `==` to avoid unexpected type conversion.
- Always convert user input to the correct data type before performing calculations.