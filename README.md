# @diotoborg/perspiciatis-voluptates-alias <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Robustly `.call.bind()` a function.

## Getting started

```sh
npm install --save @diotoborg/perspiciatis-voluptates-alias
```

## Usage/Examples

```js
const assert = require('assert');
const callBind = require('@diotoborg/perspiciatis-voluptates-alias');
const callBound = require('@diotoborg/perspiciatis-voluptates-alias/callBound');

function f(a, b) {
	assert.equal(this, 1);
	assert.equal(a, 2);
	assert.equal(b, 3);
	assert.equal(arguments.length, 2);
}

const fBound = callBind(f);

const slice = callBound('Array.prototype.slice');

delete Function.prototype.call;
delete Function.prototype.bind;

fBound(1, 2, 3);

assert.deepEqual(slice([1, 2, 3, 4], 1, -1), [2, 3]);
```

## Tests

Clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@diotoborg/perspiciatis-voluptates-alias
[npm-version-svg]: https://versionbadg.es/ljharb/@diotoborg/perspiciatis-voluptates-alias.svg
[deps-svg]: https://david-dm.org/ljharb/@diotoborg/perspiciatis-voluptates-alias.svg
[deps-url]: https://david-dm.org/ljharb/@diotoborg/perspiciatis-voluptates-alias
[dev-deps-svg]: https://david-dm.org/ljharb/@diotoborg/perspiciatis-voluptates-alias/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@diotoborg/perspiciatis-voluptates-alias#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@diotoborg/perspiciatis-voluptates-alias.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@diotoborg/perspiciatis-voluptates-alias.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@diotoborg/perspiciatis-voluptates-alias.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@diotoborg/perspiciatis-voluptates-alias
[codecov-image]: https://codecov.io/gh/ljharb/@diotoborg/perspiciatis-voluptates-alias/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@diotoborg/perspiciatis-voluptates-alias/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@diotoborg/perspiciatis-voluptates-alias
[actions-url]: https://github.com/diotoborg/perspiciatis-voluptates-alias/actions
