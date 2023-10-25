# How to fix lint:css error

For windows users who get an error message when trying to pass lint:css and
spell-check, you can go to package.json and do the following:

For CSS check: change:

"lint:css": "stylelint --fix './\*_/_.css'",

To:

"lint:css": "stylelint --fix \"./styles/style.css\"",

For spell check: Change :

"cspell './\*\*'",

To:

"spell-check": "cspell \"./\*\*\"",

[you can see the picture for more details:](https://drive.google.com/file/d/1anpmoW1iK3TUyWSpG_YEWmH4Bz3MOawQ/view?usp=sharing)
