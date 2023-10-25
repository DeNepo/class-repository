# Define URL with title(multiple words) : joinedPath vs. encodeURI()

encodeURI() function can automatically encode multiple words title with "%20".

## joinedPath

```js
// way 1: use .split() and join(). works
const WIKI = "https://en.wikipedia.org/wiki";
const title = "Pussy Cat Pussy Cat";

const joinedPath = title.split(" ").join("%20");
const URL = `${WIKI}/${joinedPath}`;
console.log(URL); //https://en.wikipedia.org/wiki/Pussy%20Cat%20Pussy%20Cat
```

## encodeURI()

```js
// way 2: use encodeURI(). works
const WIKI = "https://en.wikipedia.org/wiki";
const title = "Pussy Cat Pussy Cat";

const URL = encodeURI(`${WIKI}/${title}`);
console.log(URL); ////https://en.wikipedia.org/wiki/Pussy%20Cat%20Pussy%20Cat
```
