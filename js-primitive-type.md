## Concept

A **primitive** (primitive value, primitive data type) is data that is not an **object** and has no **methods**. In JavaScript, there are 6 primitive data types: `string`, `number`, `boolean`, `null`, `undefined`, `symbol` (new in ECMAScript 2015).

Most of the time, a primitive value is represented directly at the lowest level of the language implementation.

All primitives are **immutable**, i.e., they cannot be altered. It is important not to confuse a primitive itself with a variable assigned a primitive value. The variable may be reassigned a new value, but the existing value can not be changed in the ways that objects, arrays, and functions can be altered.
> The contnet above comes from MDN document

## Example

```javascript
// The Primitive 
let foo = 5;

// A function to change the Primitive value
function addTwo(foo) {
   foo = foo + 2;
}

// Pass our Primitive as an argument to `addTwo()` function
addTwo(foo);

// Get the current Primitive value
console.log(foo);   // 5
```
> The contnet above comes from MDN document


Primitive value has its own location in memory and can't be mutated. Once it pass to function as parameter, the `foo` declared in `addTwo` will create a new location for `foo` in function, therefore, the plus expression is not work for original `foo`.


## One more thing

#### typeof
| Type	| Result |
| ------ | ------ |
| Undefined | "undefined" |
| Null	| "object" (see below) |
| Boolean | "boolean" | 
|Number	| "number" |
| String | "string" |
|Symbol| (new in ECMAScript 2015) "symbol" |
|Host object (provided by the JS environment) | Implementation-dependent |
| Function object (implements [[Call]] in ECMA-262 terms) | "function" |
| Any other object | "object" |


#### null

`Null` is a dark shit in javascript as well. Because any primitive variable can print its correct primitive type by `typeof sth === 'type'` except `null`.

Look at the example:
```javascript
typeof null // 'object'
```

Hmmmmmm, why it cause is the `null` in javascript has its location which is `0x00`, and its primitive type is `0`, which is the type value of `Object`. So it express `object` instead of `null`. Someone has tried to correct it, but got [reject](https://archive.is/sPyGA).....

#### valueOf

A object api can magically return a primitive value from object variable. Instance of `Number` and `Stirng` should also work like this.

```javascript
function foo() { this.a = 666; this.b = 'hello'; }

foo.prototype.valueOf = function _valueOf() { return this.a };

const bar = new foo();

console.log(bar); // { [Number: 666] a: 666, b: 'halo' }

console.log(bar.b); // hello

console.log(bar + 2); // 668

bar.a = 555
console.log(bar); // { [Number: 555] a: 555, b: 'halo' }
```

## About

[valueOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/valueOf)
[Primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive)
[typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)
