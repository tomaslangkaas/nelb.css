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

```html
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
  *display: inline; /* star hack required for block elements in old IE */
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

```html
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
* Avoid markup whitespace between ghost element and centered element
* IE6+
* See [Centering in the Unknown](https://css-tricks.com/centering-in-the-unknown/) at css-tricks.com

```css
.middlealign{
  vertical-align: middle;
}

.centeralign{
  text-align: center;
}

.inlineblock{
  display: inline-block;
  zoom: 1; /* trigger hasLayout in old IE */
  *display: inline; /* star hack required for block elements in old IE */
}

html, body, .fullheight{
  height: 100%;
  margin: 0;
}
```

```html
<!doctype html>
<html>
  <body>
    <div class="fullheight centeralign">
      <div class="inlineblock fullheight middlealign"></div
      ><div class="inlineblock middlealign">
        This is centered vertically and horizontally in the viewport.
      </div>
    </div>
  </body>
</html>
```

### Share available horizontal space

```css
.float{
  float: left;
}

.bfc{
  overflow: hidden; /* create new block formatting context */
  zoom: 1; /* trigger hasLayout in old IE */
}
```

#### Group three buttons on one line
```css
.onethird{
  width: 33.33%;
}

.fullwidth{
  width: 100%;
}
```

```html
<!doctype html>
<html>
  <body>
    <div>
      <div class="float onethird">
        <button class="fullwidth">Left</button>
      </div>
      <div class="float onethird">
        <button class="fullwidth">Middle</button>
      </div>
      <div class="bfc">
        <button class="fullwidth">Right</button>
      </div>
    </div>
  </body>
</html>
```

#### Left-aligned, centered and right-aligned text on the same line
```css
.onethird{
  width: 33.33%;
}

.left{
  text-align: left;
}

.center{
  text-align: center;
}

.right{
  text-align: right;
}
```

```html
<!doctype html>
<html>
  <body>
    <div>
      <div class="float onethird left">
        Left
      </div>
      <div class="float onethird center">
        Centered
      </div>
      <div class="bfc right">
        Right
      </div>
    </div>
  </body>
</html>
```

#### Search box
#### Checklist
