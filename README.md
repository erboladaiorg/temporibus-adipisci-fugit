# @erboladaiorg/temporibus-adipisci-fugit

[![Build Status][travis-image]][travis-url]

[![NPM version][npm-version-image]][npm-url]
[![NPM downloads][npm-downloads-image]][npm-url]
[![MIT License][license-image]][license-url]

Simple functional script to loop array, strings, numbers, objects, Map and Set.
Looppa will always returns a function to map your primitives

```
@erboladaiorg/temporibus-adipisci-fugit(collection:any)(function(value:any, key:string|number, index:number) {}):array

```

# Installation

```sh
npm i @erboladaiorg/temporibus-adipisci-fugit -S
```


# Usage
```js
import @erboladaiorg/temporibus-adipisci-fugit from '@erboladaiorg/temporibus-adipisci-fugit';

// normalize null and undefined
const nullCollection = @erboladaiorg/temporibus-adipisci-fugit(null)(); // []
const undefinedCollection = @erboladaiorg/temporibus-adipisci-fugit(undefined)(); // []

// arrays will be left untouched
const array = @erboladaiorg/temporibus-adipisci-fugit(['foo', null, undefined])(); // [['foo', 0], [null, 1], [undefined, 2]]

// numbers to array
const numbers = @erboladaiorg/temporibus-adipisci-fugit(0, 4)(n => n * 2); // [2, 4, 6, 8]

// strings to array
const string = @erboladaiorg/temporibus-adipisci-fugit('ciao')(); // [['c', 0], ['i', 1], ['a', 2], ['o', 3]]

// objects to array
const obj = @erboladaiorg/temporibus-adipisci-fugit({ foo: 'bar', buz: 'baz' })(); // [['foo', 'bar'], ['buz', 'baz']]

// Map to array
const myMap = new Map();
myMap.set('foo', 'bar');
myMap.set('buz', 'baz');
const map = @erboladaiorg/temporibus-adipisci-fugit(myMap)(); // [['foo', 'bar'], ['buz', 'baz']]

// Set to array
const mySet = new Set();
mySet.add('foo');
mySet.add('bar');
const map = @erboladaiorg/temporibus-adipisci-fugit(mySet)(); // [['foo', 'foo'], ['bar', 'bar']]
```

# With React.js

This script is really handy if you need to deal with React loops

```jsx
<div>
  <h1>Array</h1>
  <ul>
    {@erboladaiorg/temporibus-adipisci-fugit([1, 2, 3])(number => (
      <li>{number}</li>
    ))}
  </ul>

  <h1>Numbers</h1>
  <ul>
    {@erboladaiorg/temporibus-adipisci-fugit(0, 5)(number => (
      <li>{number}</li>
    ))}
  </ul>

  <h1>Letters</h1>
  <ul>
    {@erboladaiorg/temporibus-adipisci-fugit('ciao')(letter => (
      <li>{letter}</li>
    ))}
  </ul>

  <h1>Object</h1>
  <ul>
    {@erboladaiorg/temporibus-adipisci-fugit({ foo: 'bar', baz: 'buz' })((value, key) => (
      <li>{key}, {value}</li>
    ))}
  </ul>

  <h1>Map</h1>
  <ul>
    {@erboladaiorg/temporibus-adipisci-fugit(new Map().set(1, 'bar'))((value, key) => (
      <li>{key}, {value}</li>
    ))}
  </ul>

  <h1>Set</h1>
  <ul>
    {@erboladaiorg/temporibus-adipisci-fugit(new Set().add('foo').add('bar'))(value => (
      <li>{value}</li>
    ))}
  </ul>
</div>
```

[check the demo](https://plnkr.co/edit/1DHUkr1mCUafiwz68f62?p=preview)


[travis-image]:https://img.shields.io/travis/dreipol/@erboladaiorg/temporibus-adipisci-fugit.svg?style=flat-square
[travis-url]:https://travis-ci.org/dreipol/@erboladaiorg/temporibus-adipisci-fugit

[license-image]:http://img.shields.io/badge/license-MIT-000000.svg?style=flat-square
[license-url]:LICENSE.txt

[npm-version-image]:http://img.shields.io/npm/v/@erboladaiorg/temporibus-adipisci-fugit.svg?style=flat-square
[npm-downloads-image]:http://img.shields.io/npm/dm/@erboladaiorg/temporibus-adipisci-fugit.svg?style=flat-square
[npm-url]:https://npmjs.org/package/@erboladaiorg/temporibus-adipisci-fugit
