# addEventListener snippet in js

## description

> the addEventListener 'listens' to specific actions by the user and triggers a
> functions when the action occurs

## application

> addEventListener allows the user to interact with a webpage in the example
> below this is done through clicking a button

## code

```html
<!-- create button on page body. use id or class to name it -->
<button type="button" id="user__btn">Start</button>
```

```javascript
// declare and assign variable for button. use querySelector, getElementById
const userBtn = document.querySelector("#user__btn");

/* apply addEventListener to button variable. the event we are 'listening' for
is a 'click' on the button. once the user clicks a function will be triggered */
userBtn.addEventListener("click", () => {
  /* define commands or actions to take place when the function is triggered. in
  our example when the user clicks the button 'start!' will log to the console */
  console.log("Start!");
});
```

## notes

- 'click' is only one of the many events we can 'listen' for with
  addEventListener. it is a versatile tool for recording user interaction
