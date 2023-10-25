# JS based simple calculator

```js
"use strict";

let operator = "";
let operation = "";
let number1;
let number2;

// accept input from the user and check if it is a number
while (isNaN(number1)) {
  number1 = parseFloat(prompt("Enter the first number: "));
}
while (
  !(
    operator === "+" ||
    operator === "-" ||
    operator === "*" ||
    operator === "/"
  )
) {
  operator = prompt("Enter valid operator ( either +, -, * or / ): ");
}
// accept input from the user and check if it is a number and a non-zero for division
while (isNaN(number2) || (number2 === 0 && operator === "/")) {
  if (number2 === 0 && operator === "/") {
    number2 = parseFloat(
      prompt("Please enter non-zero number to divide with : ")
    );
  } else number2 = parseFloat(prompt("Enter the second number: "));
}
let result; // declaration of the variable.

// use switch to define the calculator condition in JavaScript.
switch (operator) {
  case "+": // use + (addition) operator to add two numbers
    result = number1 + number2;
    operation = "The sum is : ";
    break;
  case "-": // use -  (subtraction) operator to subtract two numbers
    result = number1 - number2;
    operation = "The difference is : ";
    break;
  case "*": // use * (multiplication) operator to multiply two numbers
    result = number1 * number2;
    operation = "The product is : ";
    break;
  default:
    // The is the default operation i.e. division
    result = number1 / number2; // use / (division) operator to divide two numbers
    operation = "The  quotient is : ";
    break;
}

// display the result of the Calculator
alert(operation + result);
```
