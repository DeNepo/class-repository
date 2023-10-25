# JS Statements

## If statement

```js
const isMailSent = true;

if (isMailSent) {
  console.log("Mail sent to recipient");
}
```

An if statement accepts an expression with a set of parentheses: If the
expression evaluates to a truthy value, then the code within its code body
executes. If the expression evaluates to a falsy value, its code body will not
execute.

## Else Statement

```js
const isTaskCompleted = false;

if (isTaskCompleted) {
  console.log("Task completed");
} else {
  console.log("Task incomplete");
}
```

An else block can be added to an if block or series of if-else if blocks. The
else block will be executed only if the if condition fails.

## Else if Statement

```js
const size = 10;

if (size > 100) {
  console.log("Big");
} else if (size > 20) {
  console.log("Medium");
} else if (size > 4) {
  console.log("Small");
} else {
  console.log("Tiny");
}
```

After an initial if block, else if blocks can each check an additional
condition. An optional else block can be added after the else if block(s) to run
by default if none of the conditionals evaluated to truthy.
