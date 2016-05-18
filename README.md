## Summary

Convert html element to responsive book viewer using [nehan.js](https://github.com/tategakibunok/nehan.js).

Supports vertical writing-mode(vertical-lr, vertical-rl, horizontal-tb).

Available on IE+10, Firefox3.5+, Chrome4+, Safari6+ etc.

See [DEMO](http://tb.antiscroll.com/static/responsivook/).

## Install

Note that `nehan.js` and `nehan.css` are not included in this repository.

So get them from [nehan.js](https://github.com/tategakibunok/nehan.js).

```html
<!-- stylesheet -->
<link rel="stylesheet" href="/path/to/nehan.css">
<link rel="stylesheet" href="/path/to/responsivook.css">

<!-- scripts -->
<script src="/path/to/nehan.js"></script>
<script src="/path/to/responsivook.js"></script>
```

## Usage

```javascript
// ".post-content" is query selector.
document.addEventListener("DOMContentLoaded", function(event){
  Responsivook.start(".post-content", {
    flow:"tb-rl" // "tb-rl", "tb-lr", "lr-tb"
  });
});
```

## Options

You can set various option via second argument of `Responsivook.start`.

If you want to set viewer glocal style, use `Responsivook.setStyles` **before** `Responsivook.start`.

If you want to set viewer local style, use option `styles` in `Responsivook.start`.

See the document of nehan.js(http://tategakibunko.github.io/nehan.js/) for more detail about style object in nehan.js.


```javascript
document.addEventListener("DOMContentLoaded", function(event){
  Responsivook.start(".post-content", {
    // writing-mode for paged-media, default value is "tb-rl".
    // available values:["tb-rl", "tb-lr", "lr-tb"]
    flow:"tb-rl",

    // html preprocessor for each rendering target. not defined by default.
    onHtml:function(html){
      return html;
    },

    // color, background-color, font-size, font-family, width, height of pages.
    // if not defined, each properties are automatically defined(recommended).
    color:"#444",
    backgroundColor:"#eee",
    fontFamily:"'ヒラギノ明朝 Pro W3','Hiragino Mincho Pro','HiraMinProN-W3','IPA明朝','IPA Mincho', 'Meiryo','メイリオ','ＭＳ 明朝','MS Mincho'",
    fontSize:16,
    width:500,
    height:400,

    // viewer local styles. nothing defined by default.
    styles:{
      ".paragraph":{
        margin:{after:"1em"}
      }
    },

    // left/right button label. not defined by default.
    leftLabel:"&laquo; NEXT",
    rightLabel:"PREV &raquo;",

    // left/right button colors.
    // available values:['sea', 'dark-blue', 'red', 'rouge', 'dark', 'orange', 'sunflower', 'concrete']
    leftColor:"dark-blue",
    rightColor:"red"
  });
});
```

## License

MIT.

