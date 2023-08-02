# DSA
### 1. The prime number algorithm is a method or a set of steps used to determine whether a given number is a prime number or not. A prime number is a natural number greater than 1 that has no positive divisors other than 1 and itself.

**Algorithm :**
  1. Input: Take the number you want to check for primality. Let's call it n.
  2. Special Cases: Check if n is less than 2. If n is less than 2, it is not a prime number. Prime numbers start from 2.
  3. Divisibility Check: Initialize a variable divisor to 2. Then, loop while divisor is less than or equal to the square root of n. Check whether n is
  4. divisible by divisor (i.e., n % divisor === 0). If it is, n is not a prime number, and you can exit the loop.
  5. Primality Decision: If the loop completes without finding any divisors, then n is a prime number.

```javascript
function isPrime(n) {
  if (n < 2) {
    return false;
  }

  for (let divisor = 2; divisor * divisor <= n; divisor++) {
    if (n % divisor === 0) {
      return false;
    }
  }

  return true;
}

// Example usage:
console.log(isPrime(7));  // Output: true
console.log(isPrime(12)); // Output: false

```

**Time complexity:**
The time complexity of the isPrime function using the Trial Division algorithm is O(√n).

In the loop that checks for divisors, the loop variable divisor starts from 2 and goes up to the square root of n (i.e., divisor * divisor <= n).
The reason for going up to the square root is that if there is a factor larger than the square root of n, 
then there must be a corresponding factor smaller than the square root as well, which would have already been detected.

The number of iterations in the loop is roughly proportional to the square root of n. As a result, 
the time complexity of the isPrime function is O(√n).

For example, if n is 25, the loop will run for divisor = 2, 3, 4, 5 (up to the square root of 25), 
which is 5 iterations. If n is 100, the loop will run for divisor = 2, 3, 4, 5, 6, 7, 8, 9, 10 (up to the square root of 100), which is 10 iterations.

The Trial Division algorithm is efficient for smaller numbers, but it becomes relatively slower as n 
grows larger. For large numbers, more advanced primality testing algorithms like the Sieve of Eratosthenes or 
the Miller-Rabin primality test are preferred, as they have better time complexity for larger inputs.



