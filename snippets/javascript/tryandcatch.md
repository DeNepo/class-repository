# Try and catch

## Errors Will Happen

If you have a function that collects data and it keeps giving you a "runtime
error" at a particular spot, try surrounding that code with try catch blocks to
investigate the error object that gets returned.

The `try` statement allows you to define a block of code to be tested for errors
while it is being executed.

The `catch` statement allows you to define a block of code to be executed, if an
error occurs in the try block.

The JavaScript statements `try` and `catch` come in pairs

```js
<script>
try {
  fetchingDataFunction(); //recieves data
} catch (error) {
  console.error(error); //data not recieved
}
</script>
```

In this example we have a function that collects data from a server.

ReferenceError: Can't find variable: fetchingDataFunction
