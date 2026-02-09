<!--

@license Apache-2.0

Copyright (c) 2025 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# scattered

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Scatter a list of provided values to specified indices in a new zero-filled "generic" array.



<section class="usage">

## Usage

To use in Observable,

```javascript
scattered = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-scattered@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var scattered = require( 'path/to/vendor/umd/array-base-scattered/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-scattered@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.scattered;
})();
</script>
```

#### scattered( len, indices, values, mode )

Scatters a list of provided values to specified indices in a new zero-filled "generic" array.

```javascript
var out = scattered( 4, [ 1, 3 ], [ 20, 40 ], 'throw' );
// returns [ 0, 20, 0, 40 ]
```

The function supports the following parameters:

-   **len**: output array length.
-   **indices**: list of indices.
-   **values**: values to scatter. When `indices` contains one or more elements, `values` must be broadcast [compatible][@stdlib/ndarray/base/broadcast-shapes] with `indices` (i.e., must have either one element or the same number of elements as `indices`).
-   **mode**: index [mode][@stdlib/ndarray/base/ind].

If `indices` is an empty array, the function returns a zero-filled array.

```javascript
var out = scattered( 4, [], [ 20, 40 ], 'throw' );
// returns [ 0, 0, 0, 0 ]
```

The function supports broadcasting a `values` array containing a single element against an `indices` array containing one or more elements.

```javascript
var out = scattered( 4, [ 1, 3 ], [ 20 ], 'throw' );
// returns [ 0, 20, 0, 20 ]
```

</section>

<!-- /.usage -->

<section class="notes">

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-filled-by@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/random-base-discrete-uniform@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-scattered@umd/browser.js"></script>
<script type="text/javascript">
(function () {

// Generate an array of random indices:
var N = discreteUniform( 5, 15 );
var indices = filledBy( N, discreteUniform.factory( 0, 10 ) );
console.log( indices );

// Generate an array of random values:
var values = filledBy( N, discreteUniform.factory( 1000, 2025 ) );
console.log( values );

// Scatter a random sample of elements to a new array:
var out = scattered( 11, indices, values, 'throw' );
console.log( out );

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-base-scattered.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-base-scattered

[test-image]: https://github.com/stdlib-js/array-base-scattered/actions/workflows/test.yml/badge.svg?branch=v0.1.1
[test-url]: https://github.com/stdlib-js/array-base-scattered/actions/workflows/test.yml?query=branch:v0.1.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-base-scattered/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-base-scattered?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-base-scattered.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-base-scattered/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/array-base-scattered/tree/deno
[deno-readme]: https://github.com/stdlib-js/array-base-scattered/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/array-base-scattered/tree/umd
[umd-readme]: https://github.com/stdlib-js/array-base-scattered/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/array-base-scattered/tree/esm
[esm-readme]: https://github.com/stdlib-js/array-base-scattered/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/array-base-scattered/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-base-scattered/main/LICENSE

[@stdlib/ndarray/base/ind]: https://github.com/stdlib-js/ndarray-base-ind/tree/umd

[@stdlib/ndarray/base/broadcast-shapes]: https://github.com/stdlib-js/ndarray-base-broadcast-shapes/tree/umd

</section>

<!-- /.links -->
