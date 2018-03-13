Immutable Patch
====

Apply RFC 6902 style patches to Immutable.JS data structures, such as `Maps`, `Lists`, and `Sets`.

Forked from [`immutablepatch`](https://github.com/intelie/immutable-js-patch) which focuses more on RFC 6902 style patches, requiring string values for the paths. This fork supports [`immutable-diff`](https://github.com/tgriesser/immutable-diff) style patches.

### Getting Started

You may get the module via npm:

```
npm install immutable-patch
```

And apply JSON patches to an immutable JSON object:

```js
var Immutable = require('immutable');
var patch = require('immutable-patch');

var list = Immutable.fromJS([1, 2, [3, 4]]);
var ops = Immutable.fromJS([
  {op: 'replace', path: ['2','1'], value: 10}
]);

var result = patch(list, ops);
// var expected = Immutable.fromJS([1, 2, [3, 10]]);
```

You will probably need [`immutable-diff`](https://github.com/tgriesser/immutable-diff) to generate diff operations.
