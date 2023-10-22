# cmpstr

This lightweight npm package can be used to __calculate the similarity of strings__. It supports both the best known __Levenshtein distance__ and the slightly more accurate __Sørensen dice coefficient__.

## Install

Using Node.js install the package using shell command:

```sh
npm install cmpstr
```

## Usage

Load the package into your project:

```js
const cmpstr = require( 'cmpstr' );
```

Sample of how to use the package in your code:

```js
let str1 = 'kitten';
let str2 = 'sitting';

let distance = cmpstr.levenshteinDistance( str1, str2 );
// expected 3

let dice = cmpstr.diceCoefficient( str1, str2 );
// expected 0.3636363636363636

let closest = cmpstr.diceClosest( 'best', [
  'better', 'bestest', 'well', 'good'
] );
// expected bestest
```

## API

The npm package ``cmpstr`` supports two different methods for determining the similarity of two strings. The __Levenshtein distance__, as the minimum number of inserting, deleting and replacing operations to convert one string into another, and the __Sørensen-Dice coefficient__ to measure the similarity of two samples.

Learn more about both by visiting these links:

* [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance)
* [Sørensen-Dice coefficient](https://en.wikipedia.org/wiki/Sørensen–Dice_coefficient)

### Levenshtein distance

#### ``levenshteinDistance( a, b )``

Calculates the difference between two strings ``a`` and ``b`` and returns the Levenshtein distance as an integer value.

#### ``levenshtein( a, b )``

Returns the match percentage of two strings ``a`` and ``b``. The output value is in the range ``0..1`` as a floating point number.

#### ``levenshteinClosest( str, arr )``

Returns the best match of the string ``str`` against the array ``arr`` of passed strings. The function returns the most closely matched string found in the array.

### Sørensen-Dice coefficient

#### ``diceCoefficient( a, b )``

This function evaluates the similarity of two given strings ``a`` and ``b`` as percentage value according to the Sørensen-Dice coefficient and returns the result as floating point number.

#### ``diceClosest( str, arr )``

As another way to find the best match between the string ``str`` and a given array ``arr`` of samples, this function uses the Sørensen-Dice coefficient. It returns the most matching string as well.
