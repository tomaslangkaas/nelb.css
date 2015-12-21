# nelb.css
no explorer left behind

### Full viewport height

* Requires height to be set on <html> and <body>
* Requires requires element with class `fullheight` to be a child of <body>
* IE6+

```css
html, body, .fullheight{
  height: 100%;
}
```

````html
<html>
  <body>
    <div class="fullheight">
      This div fills the viewport.
    </div>
  </body>
</html>
```

