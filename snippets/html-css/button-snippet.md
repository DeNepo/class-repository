# A button Snippet

## A button snippet with different color and size options

### CSS

- Color options
  - `#546b40`
  - `#30ab5a`
  - `#e7b799`
  - `#d7515d`
  - `#1981f1`

```css
.btn {
  border-radius: 20px;
  overflow: hidden;
  margin: 10px;
  /*color*/
  background: #e7b799;

  /*small size
  font-size:10px;
  padding:10px;*/

  /*Normal size*/
  font-size: 16px;
  padding: 10px 25px;

  /*Medium size
  font-size:20px;
  padding:10px 30px;*/

  /*Large size
  font-size:24px;
  padding:10px 40px;*/

  /*Extra large size
  font-size:30px;
  padding:10px 35px;*/
}
.btn:hover {
  opacity: 0.4;
}
```

### HTML

`<button type="button" class="btn">click me</button>`
