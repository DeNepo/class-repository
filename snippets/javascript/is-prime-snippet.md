# A function to test whether a given number is prime or not

```js
/**
 * Given an integer number, the function will test whether this number is a prime number.
 *
 * @param {number} num - An integer number which will be checked whether prime or not.
 * @returns {boolean} - It will return true if the number is prime, otherwise false.
 */
function isPrime(num) {
  if (num <= 1) return false;
  else if (num === 2) return true;
  else {
    let n = Math.sqrt(num);
    for (let i = 2; i < n + 1; i++) {
      if (num % i === 0) return false;
    }
  }
  return true;
}

console.log(isPrime(100));
// output: false

console.log(isPrime(296797));
// output: true
```
