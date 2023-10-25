# json.stringify

Convert a JavaScript object into a string with JSON.stringify().

```js
const obj = { name: "John", age: 30, city: "New York" };
const myJSON = JSON.stringify(obj);
```

It is also possible to stringify JavaScript arrays:

```js
const arr = ["John", "Peter", "Sally", "Jane"];
const myJSON = JSON.stringify(arr);
```

What to use it for?

When storing data, the data has to be a certain format, and regardless of where
you choose to store it, text is always one of the legal formats.

JSON makes it possible to store JavaScript objects as text.

Source: W3Schools!
