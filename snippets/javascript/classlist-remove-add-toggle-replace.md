# classlist methods

## description

> the `.classlist` method allows us to interact with the tags of items in our
> html in various ways. this can be useful for many reasons the one demonstrated
> below will apply different styles to each class tag. note; the classlist
> methods are very useful in combination with `addEventListener` because it lets
> us create interactive webpages that respond visually to user actions such as
> clicking scrolling, hovering etc.

## add

> `.add()` method will add a tag to the classlist

## remove

> `.remove()` method will remove a tag from the classlist

## replace

> `.replace()` method will replace one tag with another

## toggle

> `toggle()` method will 'switch' a tag 'on' or 'off' if tag is present in
> classlist it will be disabled, if it is missing it will be enabled

### code

```js
// declare the items we want to reference in the html to variables
// this can be done with .getElementByClass .getElementById or .querySelector
const header = document.getElementByClass(".header");
const menu = document.getElementByClass(".user__menu");
const panel = document.querySelector(".panel");
const intro = document.querySelector(".intro__text");

// using the various classlist methods we can control their appearance

header.classlist.add("pop"); // enlarge header font
menu.classlist.remove("red"); // remove menu bg colour
panel.classList.replace("hide", "show"); // replace tag to reveal panel
intro.classlist.toggle("shrink"); // enlarge intro section
```

```css
/* enlarge header */
.pop {
  font-size: 4rem;
}

/* adjust menu bg */
.red {
  background-color: crimson;
}

/* hide user panel */
.hide {
  opacity: 0%;
  transition: 400ms ease-in;
}
/* reveal user panel */
.show {
  opacity: 100%;
}
/* collapse intro section */
.shrink {
  padding: 2rem;
}
```

---

## classlist methods that do not append classlist

### length

> `length()` method will not append classlist but will be qual to the number of
> classes assigned to an element

### contains

> `contains()` method will return a boolean, true if classlist contains
> specified class, false if it does not

### item

> `item()` method will return the class name at a given index. if index is empty
> will return null.

### example

```html
<div id="test" class="red blue green"></div>
```

```js
const test = document.getElementById("test");
console.log(test.classList.length()); // will log 3
console.log(test.classList.contains("yellow")); // will log false
consol.log(test.classlist.item(2)); // will log green
```

#### note

> there are many classlist methods out there. the four i described below are
> just common ones but there are many more!
