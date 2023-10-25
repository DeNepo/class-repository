# A resize user interface with CSS

## HTML code

    <!DOCTYPE html>
    <html>
    <head>
     <meta charset="utf-8" />
     <meta http-equiv="X-UA-Compatible" content="IE=edge" />
     <title>Page Title</title>
     <meta name="viewport" content="width=device-width, initial-scale=1" />
     <link rel="stylesheet" type="text/css" media="screen" href="resize.css" />
    </head>
    <body>
     <h1>The resize Property</h1>
     <div>
        <p>Let the user resize both the height and the width of this div element.</p>
        <p>To resize: Click and drag the bottom right corner of this div element.</p>
     </div>
    </body>
    </html>

## CSS code

    div {
     border: 2px solid;
     padding: 20px;
     width: 300px;
     resize: both;
     overflow: auto;
    }

The resize property in CSS specifies if an element should be resizable by the
user. You can resize your DIV vertically and horizontally with "resize:both;".
You can resize your DIV vertically with "resize:vertical;". You can resize your
DIV vertically with "resize:horizontal;".

[The example](https://www.w3schools.com/css/tryit.asp?filename=trycss3_resize)
