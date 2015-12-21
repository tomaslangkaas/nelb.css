# nelb.css
no explorer left behind

### Full viewport height

* Requires height to be set on `<html>` and `<body>`
* Requires element with class `fullheight` to be a child of `<body>`
* IE6+
* See [Understanding the `HTML` versus `BODY` Element in CSS](http://phrogz.net/css/htmlvsbody.html)

```css
html, body, .fullheight{
  height: 100%;
  margin: 0;
}
```

````html
<!doctype html>
<html>
  <body>
    <div class="fullheight">
      This div fills the viewport.
    </div>
  </body>
</html>
```

### Inline block

* Beware of markup whitespace between inline blocks
* Use `vertical-align` to keep elements aligned
* IE6+
* See [Cross-Browser Inline-Block](https://css-tricks.com/snippets/css/cross-browser-inline-block/) at css-tricks.com

```css
.inlineblock{
  display: inline-block;
  zoom: 1; /* trigger hasLayout in old IE */
  *display: inline; /* star hack requierd for block elements in old IE */
}

.width10{
  width: 10em;
}

.margin2{
  margin: 2em;
}

.topalign{
  vertical-align: top;
}
```

````html
<!doctype html>
<html>
  <body>
    <div class="inlineblock width10 margin2 topalign">
      One inlineblock,
    </div><div class="inlineblock width10 margin2 topalign">
      another inlineblock,
    </div><div class="inlineblock width10 margin2 topalign">
      and a third, all in row if the viewport is wide enough.
    </div>
  </body>
</html>
```

### Vertically centered block element

* Solution for all element dimensions
* Requires preceding ghost element
* IE6+
* See [Centering in the Unknown](https://css-tricks.com/centering-in-the-unknown/) at css-tricks.com

```css
.middlealign{
  vertical-align: middle;
}

.centeralign{
  text-align: center;
}

.font0{
  font-size: 0;
}

.inlineblock{
  display: inline-block;
  zoom: 1; /* trigger hasLayout in old IE */
  *display: inline; /* star hack requierd for block elements in old IE */
}

html, body, .fullheight{
  height: 100%;
  margin: 0;
}
```

````html
<!doctype html>
<html>
  <body>
    <div class="fullheight centeralign">
      <div class="inlineblock fullheight middlealign font0"></div>
      <div class="inlineblock middlealign">
        This is centered vertically and horizontally in the viewport.
      </div>
    </div>
  </body>
</html>
```
