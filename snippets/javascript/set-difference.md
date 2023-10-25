# Difference

Write a function that removes specific values from an array. The values to
remove are provided as a second array argument.

---

## Docstring

```js
/**
 * Creates an array of values that are in the first array, but not not in the second array.
 *
 * Repeated values are not duplicated in the return value, and the order of result values are determined by the first array.
 *
 * **Note:** This function returns a new array, and has no side-effects.
 *
 * @param {Array} [array=[]] - The array to inspect.
 * @param {Array} [values=[]] - The values to exclude.
 * @returns {Array} Returns the new array of filtered values.
 * @example
 *
 * difference([2, 1], [2, 3]); //  [1]
 *
 * @example
 *
 * difference([1, 2, 1], [2, 3]); //  [1]
 */
```

## code

```js
/**strategy:
 * 1. convert both arrays to sets that have no identical elements.
 * 2. get the set consisting of the elements that belong to the first array and that do not belong to the second array.
 * 3. convert the obtained set to a new array and return it.
 */
// 1st Try: use Set
function difference1(arr1, arr2) {
  const set1 = new Set(arr1);
  const set2 = new Set(arr2);
  const set3 = new Set([...set1].filter((x) => !set2.has(x)));
  return Array.from(set3); //way1: convert Set to Array
  // return [...set3];    // way2: convert Set to Array
}
console.log("\nTest1");
console.log("Example 1:\n", difference1([2, 1], [2, 3])); //[ 1 ]
console.log(
  "Example 2:\n",
  difference1([1, 2, 1, "abc", "3", null, 3, undefined], [2, 3]) //[ 1, 'abc', '3', null, undefined ]
);
```

```js
// 2nd Try: remove temp variable
function difference2(arr1, arr2) {
  return [...new Set(arr1)].filter((x) => !new Set(arr2).has(x));
}
console.log("\nTest2");
console.log("Example 1:\n", difference2([2, 1], [2, 3]));
console.log(
  "Example 2:\n",
  difference2([1, 2, 1, "abc", "3", null, 3, undefined], [2, 3])
);
```

## union, intersection, except

```js
const a = new Set([1, 2, 3]);
const b = new Set([4, 2, 3]);

const union = new Set([...a, ...b]);
console.log("union: ", union);

const intersect = new Set([...a].filter((ele) => b.has(ele)));
console.log("intersect: ", intersect);

const diff = new Set([...a].filter((ele) => !b.has(ele)));
console.log("diff: ", diff);
```
