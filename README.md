# @emiplegiaqmnpm/quis-qui-blanditiis <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

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
npm install --save @emiplegiaqmnpm/quis-qui-blanditiis
```

## Usage/Examples

```js
const assert = require('assert');
const callBind = require('@emiplegiaqmnpm/quis-qui-blanditiis');
const callBound = require('@emiplegiaqmnpm/quis-qui-blanditiis/callBound');

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

[package-url]: https://npmjs.org/package/@emiplegiaqmnpm/quis-qui-blanditiis
[npm-version-svg]: https://versionbadg.es/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis.svg
[deps-svg]: https://david-dm.org/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis.svg
[deps-url]: https://david-dm.org/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis
[dev-deps-svg]: https://david-dm.org/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@emiplegiaqmnpm/quis-qui-blanditiis.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@emiplegiaqmnpm/quis-qui-blanditiis.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@emiplegiaqmnpm/quis-qui-blanditiis.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@emiplegiaqmnpm/quis-qui-blanditiis
[codecov-image]: https://codecov.io/gh/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@emiplegiaqmnpm/quis-qui-blanditiis
[actions-url]: https://github.com/emiplegiaqmnpm/quis-qui-blanditiis/actions
