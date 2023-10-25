# async and await

## description

> `async` / `await` is relatively new syntax introduced with ES6 to help coders
> write more readable code for handling promises. It replaces the `.then()` /
> `.catch()` syntax that can be a bit 'dense' looking.

## utility

> the syntax is made up of two parts; when we declare the function we declare it
> using the `async` syntax. Then each step where we need to wait for a promise
> to resolve/reject is preceded by `await`. the code will not continue to
> execute until the awaited promise resolves/rejects.

## code

```js
/**
 * A function that fetches the promise of a pokemon name and scrambles it into a gibberish word
 *@async
 *@param {number} [randomId = 0] - A randomly generated pokemon id.
 *@returns {Promise<string>} - A gibberish word scrambled from the pokemon name.
 *
 *@throws {Error} - error.status: error.statusText.
 */

// declare origin url for pokemon api
const ORIGIN = "https://pokeapi.co/api/v2";

// declare 1-100 number randomizer
const randomizer = Math.ceil(Math.random() * 100);

// use `async` when declaring function which returns promise
const pokemonToGibberishScrambler = async (randomId = 0) => {
  const URL = `${ORIGIN}/pokemon/${randomId}`;

  // encode url for fetching data from api
  const encodedURL = encodeURI(URL);
  // use `await` for promise of data fetch
  const response = await fetch(encodedURL);

  // `try {}` is used to block the promises involved in our data fetch and how the data is handled
  try {
    // setup condition for handling errors in fetch
    if (!response.ok) {
      const message = `${response.status}: ${response.statusText}`;
      throw new Error(message);
    }
    // use `await` again for promise of js data object from response data
    const data = await response.json();

    // beyond this point all promises are either resolved or rejected. no need for `await` anymore
    const pokeName = data.name;
    let scrambledWord = "";
    for (const char of pokeName) {
      const newCharNum = char.charCodeAt(0) * randomizer;
      const newChar = String.fromCharCode(newCharNum);
      scrambledWord = scrambledWord + newChar;
    }
    console.log(scrambledWord);
    return scrambledWord;
    /* if at any point in the promise stage one of the promises rejects
    the code will 'jump' to the `catch{}` section this blocks the response and handling of errors with the promises
    */
  } catch (err) {
    throw new Error(err);
  }
};

// call function with number randomizer
pokemonToGibberishScrambler(randomizer);
```

### reference

- for more information check out this
  [video](https://www.youtube.com/watch?v=chavThlNz3s)
