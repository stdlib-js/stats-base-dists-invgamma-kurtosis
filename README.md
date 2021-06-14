<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

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

# Kurtosis

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] [![dependencies][dependencies-image]][dependencies-url]

> [Inverse gamma][invgamma-distribution] distribution [excess kurtosis][kurtosis].

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

The [excess kurtosis][kurtosis] for an [inverse gamma][invgamma-distribution] random variable with shape parameter `α` and rate parameter `β` is

<!-- <equation class="equation" label="eq:invgamma_kurtosis" align="center" raw="\operatorname{Kurt}\left( X \right) = \frac {30\,\alpha -66}{(\alpha -3)(\alpha -4)}" alt="Excess kurtosis for an inverse gamma distribution."> -->

<div class="equation" align="center" data-raw-text="\operatorname{Kurt}\left( X \right) = \frac {30\,\alpha -66}{(\alpha -3)(\alpha -4)}" data-equation="eq:invgamma_kurtosis">
    <img src="https://cdn.rawgit.com/stdlib-js/stdlib/7e0a95722efd9c771b129597380c63dc6715508b/lib/node_modules/@stdlib/stats/base/dists/invgamma/kurtosis/docs/img/equation_invgamma_kurtosis.svg" alt="Excess kurtosis for an inverse gamma distribution.">
    <br>
</div>

<!-- </equation> -->

when `α > 4`. Otherwise, the kurtosis is not defined.

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/stats-base-dists-invgamma-kurtosis
```

</section>

<section class="usage">

## Usage

```javascript
var kurtosis = require( '@stdlib/stats-base-dists-invgamma-kurtosis' );
```

#### kurtosis( alpha, beta )

Returns the [excess kurtosis][kurtosis] of an [inverse gamma][invgamma-distribution] distribution with parameters `alpha` (shape parameter) and `beta` (rate parameter).

```javascript
var v = kurtosis( 7.0, 5.0 );
// returns 12.0

v = kurtosis( 6.0, 12.0 );
// returns 19.0

v = kurtosis( 8.0, 2.0 );
// returns ~8.7
```

If provided `NaN` as any argument, the function returns `NaN`.

```javascript
var v = kurtosis( NaN, 2.0 );
// returns NaN

v = kurtosis( 5.0, NaN );
// returns NaN
```

If provided `alpha <= 4`, the function returns `NaN`.

```javascript
var v = kurtosis( 3.0, 1.0 );
// returns NaN

v = kurtosis( -1.0, 1.0 );
// returns NaN
```

If provided `beta <= 0`, the function returns `NaN`.

```javascript
var v = kurtosis( 5.0, 0.0 );
// returns NaN

v = kurtosis( 5.0, -1.0 );
// returns NaN
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var randu = require( '@stdlib/random-base-randu' );
var EPS = require( '@stdlib/constants-float64-eps' );
var kurtosis = require( '@stdlib/stats-base-dists-invgamma-kurtosis' );

var alpha;
var beta;
var v;
var i;

for ( i = 0; i < 10; i++ ) {
    alpha = ( randu()*10.0 ) + EPS;
    beta = ( randu()*10.0 ) + EPS;
    v = kurtosis( alpha, beta );
    console.log( 'α: %d, β: %d, Kurt(X;α,β): %d', alpha.toFixed( 4 ), beta.toFixed( 4 ), v.toFixed( 4 ) );
}
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2021. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-base-dists-invgamma-kurtosis.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-base-dists-invgamma-kurtosis

[test-image]: https://github.com/stdlib-js/stats-base-dists-invgamma-kurtosis/actions/workflows/test.yml/badge.svg
[test-url]: https://github.com/stdlib-js/stats-base-dists-invgamma-kurtosis/actions/workflows/test.yml

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-base-dists-invgamma-kurtosis/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-base-dists-invgamma-kurtosis?branch=main

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-base-dists-invgamma-kurtosis
[dependencies-url]: https://david-dm.org/stdlib-js/stats-base-dists-invgamma-kurtosis/main

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-base-dists-invgamma-kurtosis/main/LICENSE

[invgamma-distribution]: https://en.wikipedia.org/wiki/Inverse-gamma_distribution

[kurtosis]: https://en.wikipedia.org/wiki/Kurtosis

</section>

<!-- /.links -->
