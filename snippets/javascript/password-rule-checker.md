# Password Rule Checker

Demo [click here](https://passwordrulechecker.glitch.me/)

folder structure (refactored code)

- ├── src
- │ ├── init.js
- │ ├── listener.js
- │ ├──handler.js
- │ ├── logic.js
- │ ├── data.js
- ├── index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Passoword Rule Checker</title>
    <!-- Bootstrap CSS-->
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <div class="container mt-5">
      <div class="row">
        <div class="col-md-3"></div>
        <div class="col-md-6">
          <form>
            <div class="form-group m-3">
              <label for="email">Email address</label>
              <input
                type="email"
                value="sample@email.com"
                class="form-control"
                id="email"
                readonly
              />
            </div>
            <div class="form-group m-3">
              <label for="password">Password</label>
              <input
                type="password"
                class="form-control"
                id="password"
                autocomplete="off"
                placeholder="Enter your password"
              />
            </div>
            <button type="submit" class="btn btn-primary m-3">Submit</button>
            <hr />
            <progress
              min="0"
              max="100"
              value="0"
              class="form-control"
              id="progressbar"
            >
              Password
            </progress>
            <hr />
            <div>
              <small>PASSWORD SHOULD</small><br />
              <small class="text-center" id="passlength">
                be between 8-100</small
              ><br />
              <small class="text-center" id="smallLetters">
                contain at least 1 lower case </small
              ><br />
              <small class="text-center" id="capitalLetters">
                contain at least 1 upper case </small
              ><br />
              <small class="text-center" id="numbers">
                contain at least 1 number </small
              ><br />
              <small class="text-center" id="specialCharacters">
                contain at least one of *$@^#&!</small
              >
            </div>
          </form>
        </div>
      </div>
    </div>
    <script type="module" src="./src/init.js"></script>
  </body>
</html>
```

```js
/*--------------------------------------
        contents of init.js file
--------------------------------------*/
import "./listener.js";

/*--------------------------------------
        contents of listener.js file
--------------------------------------*/

import { passwordRuleHandler } from "./handler.js";

// fire event for every keyup during password typing
document
  .getElementById("password")
  .addEventListener("keyup", passwordRuleHandler);

/*--------------------------------------
        contents of handler.js file
--------------------------------------*/
// import the core logic here
import { checkPassRule } from "./logic.js";

// The event handler function is invoked by the listner during keyup event
export const passwordRuleHandler = () => {
  let password = document.getElementById("password").value;

  //call the core logic here with input password from user
  checkPassRule(password);
};

/*--------------------------------------
        contents of logic.js file
--------------------------------------*/
//import list of common passwords from the data.js file for comparison
import { data } from "./data.js";

//The core functionality is handled/executed by the logic function checkPassRule
export const checkPassRule = (password) => {
  let passLength = document.getElementById("passlength");
  let sLetters = document.getElementById("smallLetters");
  let cLetters = document.getElementById("capitalLetters");
  let numbers = document.getElementById("numbers");
  let specialChars = document.getElementById("specialCharacters");
  let passStrength = 0;
  let progressbar = document.getElementById("progressbar");
  const commonpassword = data.commonpasswords.includes(password);

  if (commonpassword) {
    passStrength = 0;
    alert(
      "warning!\n\n Your password is easily guessable. Please create a strong password."
    );
  } else {
    if (password.match(/[a-z]+/)) {
      passStrength += 1;
      sLetters.className = "text-success";
    } else {
      sLetters.className = "text-danger";
    }
    if (password.match(/[A-Z]+/)) {
      passStrength += 1;
      cLetters.className = "text-success";
    } else {
      cLetters.className = "text-danger";
    }
    if (password.match(/[0-9]+/)) {
      passStrength += 1;
      numbers.className = "text-success";
    } else {
      numbers.className = "text-danger";
    }
    if (password.match(/[*$@^#&!]+/)) {
      passStrength += 1;
      specialChars.className = "text-success";
    } else {
      specialChars.className = "text-danger";
    }

    if (password.length < 8 || password.length > 100) {
      passLength.className = "text-danger";
    } else {
      passLength.className = "text-success";
    }
  }

  switch (passStrength) {
    case 0:
      progressbar.value = 0;
      // progressbar.className = "form-control bg-white";
      break;

    case 1:
      progressbar.value = 25;
      // progressbar.className = "form-control bg-danger";
      break;

    case 2:
      progressbar.value = 50;
      // progressbar.className = "form-control bg-warning";
      break;

    case 3:
      progressbar.value = 75;
      // progressbar.className = "form-control bg-success";
      break;

    case 4:
      progressbar.value = 100;
      // progressbar.className = "form-control bg-info";
      break;
  }
};

/*--------------------------------------
        contents of data.js file
--------------------------------------*/
//The most common 100 passwords used by users across the globe
export const data = {
  commonpasswords: [
    "123456",
    "password",
    "12345678",
    "qwerty",
    "123456789",
    "12345",
    "1234",
    "111111",
    "1234567",
    "dragon",
    "123123",
    "baseball",
    "abc123",
    "football",
    "monkey",
    "letmein",
    "696969",
    "shadow",
    "master",
    "666666",
    "qwertyuiop",
    "123321",
    "mustang",
    "1234567890",
    "michael",
    "654321",
    "pussy",
    "superman",
    "1qaz2wsx",
    "7777777",
    "fuckyou",
    "121212",
    "000000",
    "qazwsx",
    "123qwe",
    "killer",
    "trustno1",
    "jordan",
    "jennifer",
    "zxcvbnm",
    "asdfgh",
    "hunter",
    "buster",
    "soccer",
    "harley",
    "batman",
    "andrew",
    "tigger",
    "sunshine",
    "iloveyou",
    "fuckme",
    "2000",
    "charlie",
    "robert",
    "thomas",
    "hockey",
    "ranger",
    "daniel",
    "starwars",
    "klaster",
    "112233",
    "george",
    "asshole",
    "computer",
    "michelle",
    "jessica",
    "pepper",
    "1111",
    "zxcvbn",
    "555555",
    "11111111",
    "131313",
    "freedom",
    "777777",
    "pass",
    "fuck",
    "maggie",
    "159753",
    "aaaaaa",
    "ginger",
    "princess",
    "joshua",
    "cheese",
    "amanda",
    "summer",
    "love",
    "ashley",
    "6969",
    "nicole",
    "chelsea",
    "biteme",
    "matthew",
    "access",
    "yankees",
    "987654321",
    "dallas",
    "austin",
    "thunder",
    "taylor",
    "matrix",
  ],
};
```

source for [100 common passwords](https://solvit.io/a86f047)
