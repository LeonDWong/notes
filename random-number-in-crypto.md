`Math.random()` is commonly used in some cases we need random number, and it's truely low-cost. But once we need a more security way to generate a random number, the `Math.random()` is likely not enough. Because `Math.random` is a pseudo random function, and it's not strong enough. `window.crypto.geRandomValues()` is a **PRNG(pseudo random number generator)**, and it's suitable for user to generate a random number in cryptographic usage.

##### e.g.:

```javascript
const array = new Uint32Array(10); // generate a 10 element of unsigned int 32 array

window.crypto.getRandomValues(array); // generate a bunch of random value

console.log(array); // 10 elements of random value number
```