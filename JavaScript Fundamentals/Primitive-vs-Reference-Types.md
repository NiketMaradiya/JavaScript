# JavaScript Primitive vs Reference Types

## Introduction

In JavaScript, every value belongs to a data type. Data types are divided into two main categories:

1. Primitive Types
2. Reference Types

Understanding the difference between these two is very important because it helps you understand how JavaScript stores data in memory and why some variables change together while others do not.

---

# JavaScript Data Types

```
JavaScript Data Types
        │
 ┌──────┴───────┐
 │              │
Primitive    Reference
```

---

# Primitive Types

Primitive types store the **actual value** directly inside the variable.

When you copy a primitive value to another variable, JavaScript creates a **new copy** of that value.

Changing one variable does **not** affect the other.

## Primitive Data Types

* String
* Number
* Boolean
* Undefined
* Null
* BigInt
* Symbol

---

## Example 1

```javascript
let a = 10;
let b = a;

console.log(a); // 10
console.log(b); // 10
```

Memory

```
a → 10
b → 10
```

Now change `b`.

```javascript
let a = 10;
let b = a;

b = 20;

console.log(a); // 10
console.log(b); // 20
```

Memory

```
a → 10
b → 20
```

The value of `a` does not change because primitive values are copied.

---

## Example 2

```javascript
let firstName = "Niket";
let anotherName = firstName;

anotherName = "Rahul";

console.log(firstName);
console.log(anotherName);
```

Output

```
Niket
Rahul
```

---

## Example 3

```javascript
let isAdmin = true;

let user = isAdmin;

user = false;

console.log(isAdmin);
console.log(user);
```

Output

```
true
false
```

---

# Real-Life Example

Imagine you photocopy a document.

```
Original Notes
↓

Copy Notes
```

If you write something on the copy, the original document does not change.

Primitive values work in the same way.

---

# Reference Types

Reference types do **not** store the actual data inside the variable.

Instead, they store the **memory address (reference)** of an object.

Multiple variables can point to the same object.

---

## Reference Types

* Object
* Array
* Function
* Date
* Map
* Set
* RegExp

---

## Object Example

```javascript
let person = {
    name: "Niket",
    age: 22
};

let user = person;
```

Memory

```
person
    \
     \
      → Object
         name: Niket
         age : 22
     /
    /
user
```

Both variables point to the same object.

---

Now modify the object.

```javascript
let person = {
    name: "Niket",
    age: 22
};

let user = person;

user.age = 30;

console.log(person.age);
console.log(user.age);
```

Output

```
30
30
```

Changing `user` also changes `person` because both variables refer to the same object.

---

# Real-Life Example

Imagine one house.

```
House
```

Two people have the address of that house.

```
Person A
   ↓

 House

   ↑
Person B
```

If Person A paints the house blue, Person B also sees the blue house because it is the same house.

Reference types work in the same way.

---

# Array Example

```javascript
let fruits = ["Apple", "Banana"];

let items = fruits;

items.push("Mango");

console.log(fruits);
console.log(items);
```

Output

```
["Apple", "Banana", "Mango"]

["Apple", "Banana", "Mango"]
```

Both variables refer to the same array.

---

# Function Example

```javascript
function hello() {
    console.log("Hello");
}

let test = hello;

test();
```

Output

```
Hello
```

Functions are also reference types.

---

# Comparing Primitive Values

```javascript
let a = 10;
let b = 10;

console.log(a === b);
```

Output

```
true
```

Both variables contain the same value.

---

# Comparing Objects

```javascript
let a = { name: "Niket" };
let b = { name: "Niket" };

console.log(a === b);
```

Output

```
false
```

Even though the data is the same, these are two different objects in memory.

---

# Same Object Example

```javascript
let a = { name: "Niket" };
let b = a;

console.log(a === b);
```

Output

```
true
```

Both variables point to the same object.

---

# Copying an Object

Instead of

```javascript
let user = person;
```

Use

```javascript
let user = { ...person };
```

Example

```javascript
let person = {
    name: "Niket",
    age: 22
};

let user = { ...person };

user.age = 30;

console.log(person.age);
console.log(user.age);
```

Output

```
22
30
```

Now both objects are independent.

---

# Copying an Array

Instead of

```javascript
let newArray = oldArray;
```

Use

```javascript
let newArray = [...oldArray];
```

Example

```javascript
let fruits = ["Apple", "Banana"];

let newFruits = [...fruits];

newFruits.push("Mango");

console.log(fruits);
console.log(newFruits);
```

Output

```
["Apple", "Banana"]

["Apple", "Banana", "Mango"]
```

---

# Primitive vs Reference

| Primitive Types                      | Reference Types                                          |
| ------------------------------------ | -------------------------------------------------------- |
| Stores actual value                  | Stores memory address                                    |
| Creates a new copy                   | Copies the reference                                     |
| Independent values                   | Shared object                                            |
| One variable does not affect another | Changes affect all variables pointing to the same object |
| Simple data                          | Complex data                                             |

---

# Primitive Types

* String
* Number
* Boolean
* Undefined
* Null
* BigInt
* Symbol

---

# Reference Types

* Object
* Array
* Function
* Date
* Map
* Set
* RegExp

---

# Easy Trick to Remember

## Primitive = Copy the Value

```javascript
let a = 10;
let b = a;
```

Each variable has its own value.

---

## Reference = Copy the Address

```javascript
let person = { name: "Niket" };
let user = person;
```

Both variables point to the same object.

---

# Final Summary

* Primitive types store the actual value.
* Copying a primitive creates a new copy.
* Changing one primitive variable does not affect another.

```javascript
let a = 10;
let b = a;

b = 20;

console.log(a); // 10
```

* Reference types store the memory address of an object.
* Copying a reference type copies the address, not the object.
* Changing the object through one variable changes it for every variable pointing to the same object.

```javascript
let person = { name: "Niket" };
let user = person;

user.name = "Rahul";

console.log(person.name); // Rahul
```

---

# Remember

> **Primitive = Copy the Value**
> **Reference = Copy the Address**
