# postcss-selector-matches [![Build Status](https://travis-ci.org/postcss/postcss-selector-matches.svg?branch=master)](https://travis-ci.org/postcss/postcss-selector-matches)

> PostCSS plugin to transform `:matches()` W3C CSS pseudo class to more compatible CSS selectors

## Installation

```console
$ npm install postcss-selector-matches
```

## Usage

```js
var postcss = require("postcss")

var output = postcss()
  .use(require("postcss-selector-matches"))
  .process(require("fs").readFileSync("input.css", "utf8"))
  .css
```

Using this `input.css`:

```css
p:matches(:first-child, .special) {
  color: red;
}
```

you will get:

```css
p:first-child, p.special {
  color: red;
}
```

**Note that if you are doing crazy selector like `p:matches(a) {}` you are likely to get crazy results (like `pa {}`)**.


---

## [Changelog](CHANGELOG.md)

## [License](LICENSE)