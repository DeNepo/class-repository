# Text encryptor

You are making a text encryptor. It should take multiple words and output a
combined version, where each word is separated by a dollar sign `$`.

For example, for the words "hello", "how", "are", "you", the output should be
`"$hello$how$are$you$"`.

<!--
`Classes` are a template for creating `objects`. They encapsulate data with code to work on that data.

This is an example of using a `class` to create `objects`.
-->

```js
class Add {
  constructor(...words) {
    this.words = words;
  }
  /* 
  `Spread syntax (...)` allows an iterable such as an array expression or string to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected, or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected.

  The `constructor` method is a special method for creating and initializing an `object` created with a `class`.
  In constructor, `this` refers to the object that is being constructed/created.
 */
  print() {
    let finalString = "";
    for (let index = 0; index < this.words.length; index++) {
      finalString += "$" + this.words[index];
    }
    /* The JavaScript `this` keyword refers to the object it belongs to. Here, in print(), `this` refers to the object that calls print().*/
    finalString += "$";
    console.log(finalString);
  }
}

const test1 = new Add("hehe", "hoho", "haha", "hihi", "huhu");
const test2 = new Add("this", "is", "awesome");
const test3 = new Add(
  "lorem",
  "ipsum",
  "dolor",
  "sit",
  "amet",
  "consectetur",
  "adipiscing",
  "elit"
);
test1.print();
test2.print();
test3.print();
```
