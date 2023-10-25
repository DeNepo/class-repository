# A method to centralize your HTML element

## HTML code

      <!DOCTYPE html>
       <html>
        <head>
          <meta charset="utf-8" />
          <meta http-equiv="X-UA-Compatible" content="IE=edge" />
          <title>Page Title</title>
          <meta name="viewport" content="width=device-width, initial-scale=1" />
          <link rel="stylesheet" type="text/css" media="screen" href="center.css" />
          <script src="main.js"></script>
        </head>
        <body>
           <div class="center"></div>
        </body>
      </html>

## CSS code

     .center {
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);

      /*use first 4 lines of CSS code above to centralize your DIV vertically and horizontally */

      background-color: rgb(65, 122, 65, 0.315);
      box-shadow: 0 4px 8px 0 rgb(0, 0, 0, 0.2), 0 6px 20px 0 rgb(0, 0, 0, 0.6);
      width: 200px;
      height: 200px;
      }

You can use first 4 lines of CSS code to centralize your DIV vertically and
horizontally. This is very useful especially when you make a web application and
want your application to appear totally centralized in the middle of page.

[The result](https://center-everything.glitch.me)
