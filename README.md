# Balanced match .

Match balanced string pairs, like `{` and `}` or `<b>` and `</b>`.


## Example

Get the first non-nested matching pair of braces:

```js
var balanced = require('balanced_match');

console.log(balanced('{', '}', 'pre{in{nested}}post'));
console.log(balanced('{', '}', 'pre{first}between{second}post'));
```

The matches are:

```bash
$ node example.js
{ start: 3, end: 14, pre: 'pre', body: 'in{nested}', post: 'post' }
{ start: 3,
  end: 9,
  pre: 'pre',
  body: 'first',
  post: 'between{second}post' }
```

## API

### var m = balanced(a, b, str)

For the first non-nested matching pair of `a` and `b` in `str`, return an
object with those keys:

* **start** the index of the first match of `a`
* **end** the index of the matching `b`
* **pre** the preamble, `a` and `b` not included
* **body** the match, `a` and `b` not included
* **post** the postscript, `a` and `b` not included

If there's no match, `undefined` will be returned.

## Installation

With [npm](https://npmjs.org) do:

```bash
npm install balanced_match
```
