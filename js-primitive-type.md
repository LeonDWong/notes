## Concept

A **primitive** (primitive value, primitive data type) is data that is not an **object** and has no **methods**. In JavaScript, there are 6 primitive data types: `string`, `number`, `boolean`, `null`, `undefined`, `symbol` (new in ECMAScript 2015).

Most of the time, a primitive value is represented directly at the lowest level of the language implementation.

All primitives are **immutable**, i.e., they cannot be altered. It is important not to confuse a primitive itself with a variable assigned a primitive value. The variable may be reassigned a new value, but the existing value can not be changed in the ways that objects, arrays, and functions can be altered.
> The contnet above comes from MDN document

## Example

```javascript
// Using a string method doesn't mutate the string
var bar = "baz";
console.log(bar);               // baz
bar.toUpperCase()
console.log(bar);               // baz

// Using an array method mutates the array
var foo = [];
console.log(foo);               // []
foo.push("plugh");
console.log(foo);               // ["plugh"]

// Assignment gives the primitive a new (not a mutated) value
bar = bar.toUpperCase();       // BAZ
```