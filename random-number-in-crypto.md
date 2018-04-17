`Math.random()` is commonly used in some cases we need random number, and it's truely low-cost. But once we need a more security way to generate a random number, the `Math.random()` is likely not enough. Because `Math.random` is a pseudo random function, and it's not strong enough. `window.crypto.geRandomValues()` is a PRNG(pseudo random number generator), and it's suitable for user to generate a random number in cryptographic usage.
e.g.:

```dkkk```