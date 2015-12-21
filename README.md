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

