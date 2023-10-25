# flex display

## overview

> flex is a collection of commands and parameters in css. flex helps us arrange
> child properties within a parent property. flex is easy to apply and highly
> adaptable to responsive design

## html

```html
<div class="container">
  <div class="child1">
    <h1>HEADLINE</h1>
  </div>
  <div class="child2">
    <p>lorem ipsum</p>
  </div>
  <div class="child3">
    <img src="www.source.com" alt="image" />
  </div>
</div>
```

## css

### divide space in flex box

````css
.container {
max-width: 1440px;
display:flex;
}

.child1 {
flex: 1;
}

.child2 {
flex: 1;
}

.child3 {
flex: 1;
}```

````

- result

> this command will make all three children fill equal space within the parent
> container the snippet above is one example of the may ways we can use flex
> display to design our pages

### order children in flex box

````css
.container {
max-width: 1440px;
display:flex;
}

.child1 {
order: 2;
}

.child2 {
order: 3;
}

.child3 {
order: 1;
}```

````

- result

> this command will reorder the children classes so that child1 is in the
> center, child2 is last and child3 is first

### learn more

- [css flex commands](https://www.youtube.com/watch?v=k32voqQhODc&list=WL&index=16)

- [more commands](https://www.youtube.com/watch?v=-Wlt8NRtOpo&list=WL&index=14&t=1351s)
