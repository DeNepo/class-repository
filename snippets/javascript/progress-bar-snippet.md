# A progress bar snippet with JavasScript and HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <title>Progress Bar</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link rel="stylesheet" type="text/css" media="screen" href="style.css" />
    <script src="script.js"></script>
  </head>
  <body>
    <label for="file">Downloading progress:</label>
    <progress value="0" max="100" id="progressBar"></progress>
  </body>
</html>
```

```js
let timeLeft = 100;
let downloadTimer = setInterval(function () {
  if (timeLeft <= 0) {
    clearInterval(downloadTimer);
  }
  document.getElementById("progressBar").value = 100 - timeLeft;
  timeLeft -= 1;
}, 100);
```

[The result](https://progress-bar-js.glitch.me)
