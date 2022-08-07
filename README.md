# @emahuni/clone-deep [![NPM version](https://img.shields.io/npm/v/@emahuni/clone-deep.svg?style=flat)](https://www.npmjs.com/package/@emahuni/clone-deep) [![NPM monthly downloads](https://img.shields.io/npm/dm/@emahuni/clone-deep.svg?style=flat)](https://npmjs.org/package/@emahuni/clone-deep) [![NPM total downloads](https://img.shields.io/npm/dt/@emahuni/clone-deep.svg?style=flat)](https://npmjs.org/package/@emahuni/clone-deep) [![Linux Build Status](https://img.shields.io/travis/emahuni/@emahuni/clone-deep.svg?style=flat&label=Travis)](https://travis-ci.org/emahuni/@emahuni/clone-deep)

> Like the original clone-deep, it will recursively (deep) clone JavaScript native types, like Object, Array, RegExp, Date as well as primitives, setters, getters and circular objects cloning.

Please consider following this project's author, [Emmanuel Mahuni](https://github.com/emahuni), and consider starring the project to show your :heart: and support.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save @emahuni/clone-deep
```

## Usage

```js
const cloneDeep = require('@emahuni/clone-deep');

let obj = { a: 'b' };
let arr = [obj];

let copy = cloneDeep(arr);
obj.c = 'd';

console.log(copy);
//=> [{ a: 'b' }]

console.log(arr);
//=> [{ a: 'b', c: 'd' }]

obj.e = obj;
copy = cloneDeep(arr);

console.log(copy);
//=> [{ a: 'b', c: 'd', e: {...} }] // handles circular arrays and objects cloning
```

## Heads up!

The last argument specifies whether to clone instances (objects that are from a custom class or are not created by the `Object` constructor. This value may be `true` or the function use for cloning instances.

When an `instanceClone` function is provided, it will be invoked to clone objects that are not "plain" objects (as defined by [isPlainObject](#isPlainObject)`isPlainObject`). If `instanceClone` is not specified, this library will not attempt to clone non-plain objects, and will simply copy the object reference.

## Attribution

Based on [jonschlinkert's](https://github.com/jonschlinkert/clone-deep) that was...
initially based on [mout's](https://github.com/mout/mout) implementation of deepClone.

## About

<details>
<summary><strong>Contributing</strong></summary>

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

</details>

<details>
<summary><strong>Running Tests</strong></summary>

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

</details>

### Contributors

| **Commits** | **Contributor** |  
| -- | --- |  
| 5  | [emahuni](https://github.com/emahuni) |  
| 46 | [jonschlinkert](https://github.com/jonschlinkert) |  
| 2 | [yujunlong2000](https://github.com/yujunlong2000) |  

### Author

**Emmanuel Mahuni**

* [GitHub Profile](https://github.com/emahuni)
* [Twitter Profile](https://twitter.com/emahuni)
* [LinkedIn Profile](https://linkedin.com/in/emahuni)

### License

Copyright © 2022, [Emmanuel Mahuni](https://github.com/emahuni).
Released under the [MIT License](LICENSE).

***