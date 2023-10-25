# test assertions

## description / application

> test assertions are code shorthand that allow writing concise and clear unit
> tests. this code is external to javascript and requires a testing framework to
> execute.

## code

- example function:

````js
// the function below compares the length of two strings
// and returns the longer of the two
function longerString(text1 = '', text2 = '') {
if(text1.length > text2.length) {
  return text1;
}
return text2;
} ```
````

- test assertions:

```js
// a group of tests is called a 'testing suit'
// for every category of tests we will use the describe assertion
describe("testing suit for longerString function", () => {
  // a describe assert will include a description of what is tested(string) and a set of tests
  // inside of the large testing suit category we will have smaller categories of tests
  describe("returns longer string", () => {
    // inside every category of tests we will have specific case tests
    it("three is longer than two", () => {
      // an it assertion is a case specific assertion.
      // it checks specific input against a specific expected output
      expect(longerString("three", "two")).toEqual("three");
      // the expect().toEqual() calls the function with a specific arguments
      // and compares the return with an expected output.
      // if the expected value is equal to the toEqual value the test will pass.
      // if they are not equal the test will fail.
    });
  });
});
```
