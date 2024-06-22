`Math.random()` returns a floating-point number greater than or equal to 0, but strictly less than 1.

It utilizes an algorithm to generate these pseudo-numbers, but they are not truly random in a cryptographic sense. This means they can be predictable for certain applications.

## Getting a random number between 1 and x

The way to do this is to multiply the `Math.random()` with the **range** to scale it. Range of numbers between max and min is (max - min + 1). So from 1 and 6 that would be $6-1+1 = 6$ . Remember 6 technically is excluded because in original 1 is excluded. 

**Edge cases**
When we get something close to 0 or something really close to max.
1. **Close to zero** :  We add the min at the end to compensate for that
2. **Close to max** : We floor everything so max value is range value. So we add min to the result of random and then we floor the whole thing.


> [!Example] Between 1 and 6
> range = 6, min = 1, max = 6
> Large possible value = 5.99 + 1 = 6.99; floored down to 6

```js
function getRandomNumberBetween(min, max) {
  // generates a random number between 0 (inclusive) and 1 (exclusive)
  const randomDecimal = Math.random();

  // Multiply random decimal by the range (max - min + 1) and floor the result
  // to get a random integer within the range.
  const randomNumber = Math.floor(randomDecimal * (max - min + 1) + min);

  return randomNumber;
}

// Get a random number between 1 and 6
const randomNum = getRandomNumberBetween(1, 6);
console.log(randomNum); // This will output a random number between 1 and 6

```

> [!Example] Between 2 and 10
> range = 9, min = 2, max = 10
> Large possible value = 8.99 + 2 = 10.99; floored down to 10 (max)
> Small possible value = 0.5 + 2 = 2.5; floored down to 2 (min)

> [!Warning] Argument
> `Math.random()` does not take any arguments