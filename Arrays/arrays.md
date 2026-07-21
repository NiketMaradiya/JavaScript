# JavaScript Arrays & Array Methods (Detailed Guide)

## Arrays

An **Array** is an ordered collection of values stored in a single
variable.

``` js
const fruits = ["Apple","Banana","Orange"];
```

### Creating Arrays

``` js
const a = [1,2,3];
const b = new Array(1,2,3);
```

### Access

``` js
const arr = [10,20,30];
console.log(arr[0]); //10
console.log(arr.at(-1)); //30
```

### Update

``` js
arr[1] = 99;
```

### Length

``` js
console.log(arr.length);
```

------------------------------------------------------------------------

# map()

Creates a **new array** by transforming every element.

## Syntax

``` js
array.map((value,index,array)=>{})
```

## Example

``` js
const nums=[1,2,3];
const doubled=nums.map(n=>n*2);
console.log(doubled); //[2,4,6]
```

## Example with objects

``` js
const users=[{name:"John"},{name:"Sara"}];
console.log(users.map(u=>u.name));
```

## Common Errors

### Missing return

``` js
nums.map(n=>{
    n*2;
});
```

Output

``` text
[undefined, undefined, undefined]
```

Correct

``` js
nums.map(n=>{
   return n*2;
});
```

### Expecting original array to change

``` js
nums.map(n=>n*2);
console.log(nums);
```

Original array remains unchanged.

Time Complexity: O(n)

------------------------------------------------------------------------

# filter()

Returns elements matching a condition.

``` js
const nums=[10,20,30,40];
console.log(nums.filter(n=>n>20));
```

Output

``` text
[30,40]
```

### Error

``` js
nums.filter(n=>{
   n>20;
});
```

Returns `[]` because `return` is missing.

Time Complexity: O(n)

------------------------------------------------------------------------

# reduce()

Reduces array to a single value.

``` js
const nums=[1,2,3];
const sum=nums.reduce((acc,n)=>acc+n,0);
console.log(sum);
```

Output

``` text
6
```

### Error

``` js
[].reduce((a,b)=>a+b);
```

Throws

``` text
TypeError: Reduce of empty array with no initial value
```

Correct

``` js
[].reduce((a,b)=>a+b,0);
```

Time Complexity: O(n)

------------------------------------------------------------------------

# find()

Returns first matching element.

``` js
const arr=[10,20,30];
console.log(arr.find(x=>x>15));
```

Output

``` text
20
```

If no match:

``` text
undefined
```

Common mistake: expecting all matching values. Use `filter()` instead.

------------------------------------------------------------------------

# findIndex()

Returns first matching index.

``` js
const arr=[10,20,30];
console.log(arr.findIndex(x=>x===20));
```

Output

``` text
1
```

No match returns `-1`.

Always check:

``` js
if(index!==-1){
   // safe
}
```

------------------------------------------------------------------------

# some()

Returns true if **at least one** element matches.

``` js
[1,2,3].some(x=>x>2);
```

Output

``` text
true
```

Returns only boolean, not array.

------------------------------------------------------------------------

# every()

Returns true if **all** elements satisfy condition.

``` js
[2,4,6].every(x=>x%2===0);
```

Output

``` text
true
```

------------------------------------------------------------------------

# sort()

Default sorting is alphabetical.

Wrong

``` js
[100,2,50].sort();
```

Output

``` text
[100,2,50]
```

Correct

``` js
[100,2,50].sort((a,b)=>a-b);
```

Output

``` text
[2,50,100]
```

Descending

``` js
.sort((a,b)=>b-a)
```

Modifies original array.

------------------------------------------------------------------------

# reverse()

``` js
const arr=[1,2,3];
arr.reverse();
```

Output

``` text
[3,2,1]
```

Changes original array.

------------------------------------------------------------------------

# flat()

Flattens nested arrays.

``` js
[1,[2,[3]]].flat(Infinity);
```

Output

``` text
[1,2,3]
```

------------------------------------------------------------------------

# flatMap()

Equivalent to

``` js
map().flat()
```

Example

``` js
[1,2].flatMap(x=>[x,x*2]);
```

Output

``` text
[1,2,2,4]
```

------------------------------------------------------------------------

# slice()

Returns a copy.

``` js
const arr=[10,20,30,40];
arr.slice(1,3);
```

Output

``` text
[20,30]
```

Original array unchanged.

------------------------------------------------------------------------

# splice()

Adds, removes or replaces elements.

Remove

``` js
const arr=[10,20,30];
arr.splice(1,1);
```

Output

``` text
[10,30]
```

Insert

``` js
arr.splice(1,0,20);
```

Replace

``` js
arr.splice(1,1,99);
```

Returns removed elements, not updated array.

------------------------------------------------------------------------

# fill()

``` js
const arr=[1,2,3];
arr.fill(0);
```

Output

``` text
[0,0,0]
```

Partial

``` js
arr.fill(5,1,2);
```

------------------------------------------------------------------------

# copyWithin()

Copies part of an array inside itself.

``` js
const arr=[1,2,3,4,5];
arr.copyWithin(0,3);
```

Output

``` text
[4,5,3,4,5]
```

Modifies original array.

------------------------------------------------------------------------

# at()

Supports negative indexes.

``` js
const arr=[10,20,30];
arr.at(-1);
```

Output

``` text
30
```

------------------------------------------------------------------------

# Comparison Table

  Method       Returns         Original Modified
  ------------ --------------- -------------------
  map          New array       No
  filter       New array       No
  reduce       Single value    No
  find         Element         No
  findIndex    Index           No
  some         Boolean         No
  every        Boolean         No
  sort         Array           Yes
  reverse      Array           Yes
  flat         New array       No
  flatMap      New array       No
  slice        New array       No
  splice       Removed items   Yes
  fill         Array           Yes
  copyWithin   Array           Yes
  at           Element         No

# Interview Tips

-   map vs forEach: map returns a new array.
-   filter vs find: filter returns all matches; find returns the first.
-   slice vs splice: slice does not modify the array; splice modifies
    it.
-   sort needs a compare function for numbers.
-   Always provide an initial value to reduce when the array may be
    empty.
