# JavaScript Objects (Complete Guide)

## Topics Covered

1. Object Creation
2. Object Methods
3. Destructuring
4. Spread & Rest
5. Optional Chaining
6. Nullish Coalescing
7. Object.keys()
8. Object.values()
9. Object.entries()
10. Object.assign()
11. Object.freeze()
12. Object.seal()
13. Object.hasOwn()

---

# 1. Object Creation

Objects store data as **key-value pairs**.

## Syntax

```javascript
const objectName = {
    key: value
};
```

## Example

```javascript
const person = {
    name: "John",
    age: 25,
    city: "London"
};

console.log(person);
```

### Output

```javascript
{
  name: "John",
  age: 25,
  city: "London"
}
```

## Access Properties

### Dot Notation

```javascript
console.log(person.name);
```

Output

```
John
```

### Bracket Notation

```javascript
console.log(person["age"]);
```

Output

```
25
```

## Add Property

```javascript
person.country = "UK";
```

## Update Property

```javascript
person.age = 26;
```

## Delete Property

```javascript
delete person.city;
```

### Common Errors

#### Error 1

```javascript
const user = {};

console.log(user.address.city);
```

Output

```
TypeError:
Cannot read properties of undefined
```

Solution

```javascript
console.log(user.address?.city);
```

---

# 2. Object Methods

Objects can store functions.

```javascript
const person = {
    name: "John",

    greet() {
        console.log("Hello " + this.name);
    }
};

person.greet();
```

Output

```
Hello John
```

### Common Error

Using Arrow Function with this

```javascript
const person = {
    name: "John",

    greet: () => {
        console.log(this.name);
    }
};
```

Output

```
undefined
```

Correct

```javascript
const person = {
    name: "John",

    greet() {
        console.log(this.name);
    }
};
```

---

# 3. Object Destructuring

Extract object properties.

```javascript
const user = {
    name: "Rahul",
    age: 22
};

const { name, age } = user;

console.log(name);
console.log(age);
```

Output

```
Rahul
22
```

### Rename Variable

```javascript
const { name: username } = user;
```

### Default Value

```javascript
const { city = "Ahmedabad" } = user;
```

### Nested Destructuring

```javascript
const data = {
    address: {
        city: "Delhi"
    }
};

const {
    address: { city }
} = data;
```

### Common Error

```javascript
const user = {};

const {
    address: { city }
} = user;
```

Output

```
TypeError
```

Solution

```javascript
const {
    address: { city } = {}
} = user;
```

---

# 4. Spread (...)

Copy Object

```javascript
const user = {
    name: "Rahul"
};

const copy = {
    ...user
};
```

Merge Objects

```javascript
const a = {
    x: 1
};

const b = {
    y: 2
};

const result = {
    ...a,
    ...b
};
```

Overwrite

```javascript
const result = {
    ...a,
    x: 100
};
```

---

# Rest (...)

Collect Remaining Properties

```javascript
const user = {
    name: "Rahul",
    age: 22,
    city: "Delhi"
};

const {
    name,
    ...others
} = user;
```

### Common Error

```javascript
const {
    ...rest,
    name
} = user;
```

Output

```
SyntaxError
```

Rest must always be last.

---

# 5. Optional Chaining

Safely access nested properties.

```javascript
const user = {};

console.log(user.address?.city);
```

Output

```
undefined
```

### Multiple Levels

```javascript
user.company?.address?.city;
```

### Calling Method

```javascript
user.sayHello?.();
```

### Common Error

Wrong

```javascript
user?.address.city;
```

Correct

```javascript
user?.address?.city;
```

---

# 6. Nullish Coalescing

Returns default value only if left side is null or undefined.

```javascript
const name = null;

console.log(name ?? "Guest");
```

Output

```
Guest
```

Difference from ||

```javascript
console.log(0 || 100);
```

Output

```
100
```

```javascript
console.log(0 ?? 100);
```

Output

```
0
```

### Common Error

```javascript
null || undefined ?? "Hello";
```

Output

```
SyntaxError
```

Correct

```javascript
(null || undefined) ?? "Hello";
```

---

# 7. Object.keys()

Returns array of keys.

```javascript
const user = {
    name: "John",
    age: 25
};

console.log(Object.keys(user));
```

Output

```javascript
["name", "age"]
```

Loop

```javascript
Object.keys(user).forEach(key => {
    console.log(key);
});
```

### Error

```javascript
Object.keys(null);
```

Output

```
TypeError
```

---

# 8. Object.values()

Returns array of values.

```javascript
console.log(Object.values(user));
```

Output

```javascript
["John", 25]
```

### Error

```javascript
Object.values(undefined);
```

Output

```
TypeError
```

---

# 9. Object.entries()

Returns array of key-value pairs.

```javascript
console.log(Object.entries(user));
```

Output

```javascript
[
    ["name", "John"],
    ["age", 25]
]
```

Loop

```javascript
for (const [key, value] of Object.entries(user)) {
    console.log(key, value);
}
```

---

# 10. Object.assign()

Merge Objects

```javascript
const result = Object.assign({}, a, b);
```

Copy Object

```javascript
const copy = Object.assign({}, user);
```

### Wrong

```javascript
const copy = Object.assign(user);
```

Returns same reference.

---

# 11. Object.freeze()

Prevents:

- Adding
- Updating
- Deleting

```javascript
Object.freeze(user);
```

### Error

```javascript
user.name = "ABC";
```

Ignored (or error in strict mode)

### Important

Freeze is **Shallow**.

Nested objects still change.

---

# 12. Object.seal()

Prevents

- Adding
- Deleting

Allows

- Updating

```javascript
Object.seal(user);
```

Example

```javascript
user.name = "John";
```

Works

```javascript
user.age = 20;
```

Ignored

---

# Difference

| Feature | Freeze | Seal |
|----------|--------|------|
| Add | ❌ | ❌ |
| Delete | ❌ | ❌ |
| Update | ❌ | ✅ |

---

# 13. Object.hasOwn()

Checks own property.

```javascript
const user = {
    name: "Rahul"
};

console.log(Object.hasOwn(user, "name"));
```

Output

```
true
```

```javascript
console.log(Object.hasOwn(user, "age"));
```

Output

```
false
```

### Why Use It?

Better than

```javascript
user.hasOwnProperty("name");
```

because `Object.hasOwn()` also works with objects created using `Object.create(null)`.

---

# Common Interview Questions

### Q1. Difference between Object.freeze() and Object.seal()?

- **freeze()** → No add, update, or delete.
- **seal()** → No add or delete, but updates are allowed.

### Q2. Difference between Spread and Object.assign()?

- Spread (`...`) creates a new object more concisely.
- `Object.assign()` copies properties into a target object and can mutate it if the target isn't empty.

### Q3. Difference between `??` and `||`?

- `||` treats all falsy values (`0`, `""`, `false`, `NaN`, `null`, `undefined`) as needing the right-hand value.
- `??` only falls back for `null` or `undefined`.

### Q4. Difference between Optional Chaining and Nullish Coalescing?

- `?.` safely accesses nested properties or methods.
- `??` provides a default value when the result is `null` or `undefined`.

---

# Best Practices

- Use object literals (`{}`) for most object creation.
- Prefer destructuring for cleaner code.
- Use spread (`...`) to copy or merge objects.
- Use optional chaining (`?.`) to avoid runtime errors.
- Use `??` instead of `||` when `0`, `false`, or `""` are valid values.
- Use `Object.hasOwn()` instead of `hasOwnProperty()`.
- Remember that `Object.freeze()` and `Object.seal()` are **shallow**, not deep.
