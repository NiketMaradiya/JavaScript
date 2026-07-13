# JavaScript `for...in` Loop

The `for...in` loop is used to **iterate (loop) through the properties (keys) of an object**.

It is mainly used with **Objects**.

---

# Syntax

```javascript
for (let key in object) {
    // code
}
```

### Explanation

- `for` → Starts the loop.
- `let key` → Variable that stores the current property name.
- `in` → Tells JavaScript to iterate over object properties.
- `object` → The object whose keys you want to loop through.

---

# Why Use `for...in`?

Suppose you have an object:

```javascript
const student = {
    name: "Niket",
    age: 20,
    city: "Ahmedabad"
};
```

Without `for...in`:

```javascript
console.log(student.name);
console.log(student.age);
console.log(student.city);
```

Output

```
Niket
20
Ahmedabad
```

This is fine for 3 properties.

But imagine an object has **100 properties**.

Writing 100 `console.log()` statements is not practical.

Instead, use `for...in`.

---

# Example 1: Print Keys

```javascript
const student = {
    name: "Niket",
    age: 20,
    city: "Ahmedabad"
};

for (let key in student) {
    console.log(key);
}
```

Output

```
name
age
city
```

The loop returns only the **property names (keys)**.

---

# Example 2: Print Values

```javascript
const student = {
    name: "Niket",
    age: 20,
    city: "Ahmedabad"
};

for (let key in student) {
    console.log(student[key]);
}
```

Output

```
Niket
20
Ahmedabad
```

Notice:

```javascript
student[key]
```

This is called **Bracket Notation**.

It uses the value stored inside the variable `key`.

---

# Example 3: Print Key and Value

```javascript
const student = {
    name: "Niket",
    age: 20,
    city: "Ahmedabad"
};

for (let key in student) {
    console.log(key + " : " + student[key]);
}
```

Output

```
name : Niket
age : 20
city : Ahmedabad
```

---

# Memory Visualization

Object

```javascript
const student = {
    name: "Niket",
    age: 20,
    city: "Ahmedabad"
};
```

Memory

```
student
   |
   +----------------------+
   | name → Niket         |
   | age  → 20            |
   | city → Ahmedabad     |
   +----------------------+
```

Loop Execution

### First Iteration

```
key = "name"

student[key]

↓

student["name"]

↓

"Niket"
```

### Second Iteration

```
key = "age"

↓

student["age"]

↓

20
```

### Third Iteration

```
key = "city"

↓

student["city"]

↓

Ahmedabad
```

---

# Example 4: Employee Object

```javascript
const employee = {
    id: 101,
    name: "Rahul",
    salary: 50000,
    department: "IT"
};

for (let key in employee) {
    console.log(key + " : " + employee[key]);
}
```

Output

```
id : 101
name : Rahul
salary : 50000
department : IT
```

---

# Example 5: Product Object

```javascript
const product = {
    name: "Laptop",
    brand: "Dell",
    price: 65000,
    stock: 15
};

for (let key in product) {
    console.log(key + " : " + product[key]);
}
```

Output

```
name : Laptop
brand : Dell
price : 65000
stock : 15
```

---

# Example 6: Calculate Total Marks

```javascript
const marks = {
    math: 90,
    science: 85,
    english: 88
};

let total = 0;

for (let subject in marks) {
    total += marks[subject];
}

console.log(total);
```

Output

```
263
```

---

# Example 7: Count Properties

```javascript
const person = {
    name: "Amit",
    age: 25,
    city: "Delhi",
    job: "Developer"
};

let count = 0;

for (let key in person) {
    count++;
}

console.log(count);
```

Output

```
4
```

---

# Example 8: `for...in` with Array

```javascript
const fruits = ["Apple", "Banana", "Mango"];

for (let index in fruits) {
    console.log(index);
}
```

Output

```
0
1
2
```

To print values:

```javascript
const fruits = ["Apple", "Banana", "Mango"];

for (let index in fruits) {
    console.log(fruits[index]);
}
```

Output

```
Apple
Banana
Mango
```

Although this works,

**Do NOT use `for...in` for arrays.**

Use **for...of** instead.

---

# Example 9: Real World Example

Suppose data comes from an API.

```javascript
const user = {
    id: 1,
    name: "Niket",
    email: "niket@gmail.com",
    role: "Admin"
};

for (let key in user) {
    console.log(`${key}: ${user[key]}`);
}
```

Output

```
id: 1
name: Niket
email: niket@gmail.com
role: Admin
```

---

# `for...in` vs `for...of`

| `for...in` | `for...of` |
|------------|------------|
| Used for Objects | Used for Arrays, Strings, Maps, Sets |
| Returns Keys | Returns Values |
| Best for Objects | Best for Arrays |
| Can loop over array indexes | Loops over array values |

Example

```javascript
const arr = ["A", "B", "C"];

for (let i in arr) {
    console.log(i);
}
```

Output

```
0
1
2
```

```javascript
const arr = ["A", "B", "C"];

for (let value of arr) {
    console.log(value);
}
```

Output

```
A
B
C
```

---

# Common Mistake 1

❌ Wrong

```javascript
const student = {
    name: "Niket",
    age: 20
};

for (let key in student) {
    console.log(student.key);
}
```

Output

```
undefined
undefined
```

Because JavaScript looks for a property named `"key"`.

✅ Correct

```javascript
for (let key in student) {
    console.log(student[key]);
}
```

Output

```
Niket
20
```

---

# Common Mistake 2

Using `for...in` with arrays.

```javascript
const numbers = [10, 20, 30];

for (let index in numbers) {
    console.log(index);
}
```

Output

```
0
1
2
```

If you want values,

Use

```javascript
for (let value of numbers) {
    console.log(value);
}
```

Output

```
10
20
30
```

---

# Object.hasOwn()

Sometimes objects inherit properties.

To access only the object's own properties:

```javascript
const student = {
    name: "Niket",
    age: 20
};

for (let key in student) {
    if (Object.hasOwn(student, key)) {
        console.log(key, student[key]);
    }
}
```

Output

```
name Niket
age 20
```

---

# When to Use `for...in`

✅ Loop through object properties.

✅ Print object keys.

✅ Print key-value pairs.

✅ Count object properties.

✅ Read dynamic object data.

---

# When NOT to Use `for...in`

❌ Arrays

❌ Strings

❌ Maps

❌ Sets

For these, use **for...of**.

---

# Advantages

- Easy to loop through objects.
- No need to know property names.
- Great for dynamic data.
- Simple syntax.
- Can access both keys and values.

---

# Disadvantages

- Returns keys, not values.
- Not recommended for arrays.
- Can iterate inherited properties unless checked with `Object.hasOwn()`.

---

# Interview Questions

## 1. What is `for...in`?

**Answer:**

`for...in` is a loop used to iterate through the enumerable property names (keys) of an object.

---

## 2. What does `for...in` return?

**Answer:**

It returns **keys (property names)**.

---

## 3. How do you get values in `for...in`?

**Answer**

```javascript
object[key]
```

---

## 4. Can `for...in` be used with arrays?

**Answer**

Yes, but it is **not recommended**.

Use **for...of** instead.

---

## 5. Difference between `for...in` and `for...of`?

| `for...in` | `for...of` |
|------------|------------|
| Returns Keys | Returns Values |
| Used for Objects | Used for Arrays & Iterables |

---

# Summary

- `for...in` is mainly used for **Objects**.
- It returns **property names (keys)**.
- Use **object[key]** to get the value.
- Best for object iteration.
- Avoid using it for arrays.
- For arrays, use **for...of** or **forEach()**.