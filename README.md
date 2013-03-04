# QR.js
### Simple HTML5 Canvas-based QR Code generation

Based on [jsqrencode](https://code.google.com/p/jsqrencode/). Provides an API that's easier to work with. It requires ES5/Canvas so it only works on IE9+.

License: [GPLv3](http://www.gnu.org/licenses/gpl.html).

### How to Use

``` js

// draw into a canvas
QR.draw('Hello world!', document.getElementById('qr-canvas'));

// make an image
document.body.append(QR.makeImage('Hello again!'));

// set options so you can omit them for later use
QR.size = 500;
QR.ecclevel = 4;
QR.canvas = document.getElementById('qr-canvas'); // make sure your canvas is the right size.
QR.draw('Now it\'s easier!');

```


### API

---

``` js
QR.draw(string, canvas [, size] [, ecclevel])
```

Draws directly into an existing canvas element.

Arguments:

- `string`: string to encode.
- `canvas`: a canvas DOM element. Optional if you have set `QR.canvas`.
- `size`: size of code in pixels. Default: fill canvas.
- `ecclevel`: Error Correction Capability level. Range: 1~4. Default: 2.

---

``` js
QR.makeImage(string [, size] [, ecclevel])
QR.toDataURL(string [, size] [, ecclevel])
```

Returns an image DOM element, or get the DataURL string.

Arguments:

- `string`: string to encode.
- `size`: size of image in pixels. Default: 300.
- `ecclevel`: Error Correction Capability level. Range: 1~4. Default: 2.

---

``` js
QR.getFrame(string)
```

Returns an array containing value for each grid in the generated code. Black grids have value 1, empty ones are undefined.

Arguments:

- `string`: string to encode.