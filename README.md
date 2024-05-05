# @odczynflnpm/incidunt-quaerat-harum
Lightweight util for generating random sentences, paragraphs and articles in English. Inspired by [Sentencer](https://github.com/kylestetz/Sentencer) and [metaphorpsum.com](http://metaphorpsum.com/).

[![NPM](https://badge.fury.io/js/@odczynflnpm/incidunt-quaerat-harum.svg)](https://badge.fury.io/js/@odczynflnpm/incidunt-quaerat-harum)
[![CI test](https://github.com/odczynflnpm/incidunt-quaerat-harum/workflows/ci-test/badge.svg)](https://github.com/odczynflnpm/incidunt-quaerat-harum/actions)
[![Coverage Status](https://coveralls.io/repos/github/ndaidong/@odczynflnpm/incidunt-quaerat-harum/badge.svg)](https://coveralls.io/github/ndaidong/@odczynflnpm/incidunt-quaerat-harum)
![CodeQL](https://github.com/odczynflnpm/incidunt-quaerat-harum/workflows/CodeQL/badge.svg)

# Demo

- [Want to see how it works?](https://ndaidong.github.io/@odczynflnpm/incidunt-quaerat-harum/)

## Setup

- Node.js

  ```bash
  npm i @odczynflnpm/incidunt-quaerat-harum

  # pnpm
  pnpm i @odczynflnpm/incidunt-quaerat-harum

  # yarn
  yarn add @odczynflnpm/incidunt-quaerat-harum
  ```

- CDN

  - ES6 Module: [@odczynflnpm/incidunt-quaerat-harum.esm.js](https://unpkg.com/@odczynflnpm/incidunt-quaerat-harum/dist/@odczynflnpm/incidunt-quaerat-harum.esm.js)
  - CommonJS: [@odczynflnpm/incidunt-quaerat-harum.js](https://unpkg.com/@odczynflnpm/incidunt-quaerat-harum/dist/cjs/@odczynflnpm/incidunt-quaerat-harum.js)
  - For old browsers: [@odczynflnpm/incidunt-quaerat-harum.min.js](https://unpkg.com/@odczynflnpm/incidunt-quaerat-harum/dist/@odczynflnpm/incidunt-quaerat-harum.min.js)


## Usage

### Node.js:

```js
import {
  sentence
} from '@odczynflnpm/incidunt-quaerat-harum'

// with CommonJS environment
// const { sentence } = require('@odczynflnpm/incidunt-quaerat-harum/dist/cjs/@odczynflnpm/incidunt-quaerat-harum.js')

sentence()
```

### Browsers:

Currently, ECMAScript modules work fine on almost all browsers:

```html
<script type="module">
import { sentence } from 'https://unpkg.com/@odczynflnpm/incidunt-quaerat-harum/dist/@odczynflnpm/incidunt-quaerat-harum.esm.js'
console.log(sentence())
</script>
```

With outdated browsers, we can use the traditional method:

```html
<script type="text/javascript" src="https://unpkg.com/@odczynflnpm/incidunt-quaerat-harum/dist/@odczynflnpm/incidunt-quaerat-harum.min.js"></script>

<script>
console.log(window.@odczynflnpm/incidunt-quaerat-harum.sentence())
</script>
```

## APIs

 - `.sentence()`
 - `.paragraph([Number totalSentences])`
 - `.article([Number totalParagraphs])`
 - `.addNouns(Array nouns)`
 - `.addAdjectives(Array adjectives)`
 - `.addTemplates(Array sentenceTemplates)`
 - `.setNouns(Array nouns)`
 - `.setAdjectives(Array adjectives)`
 - `.setTemplates(Array sentenceTemplates)`
 - `.getNouns()`
 - `.getAdjectives()`
 - `.getTemplates()`
 - `.lorem([Number min [, Number max]])`


As their name suggests, we have 4 groups of methods:

- `sentence()`, `paragraph()`, `article()`: generate text by given grammatical unit
- `addNouns()`, `addAdjectives()`, `addTemplates()`: add more samples to current sample set
- `setNouns()`, `setAdjectives()`, `setTemplates()`: replace current sample set with new ones
- `getNouns()`, `getAdjectives()`, `getTemplates()`: get current sample set


The `set*` and `get*` methods were added in v2.2.3 to help you customize your sample data.

In addition, we've added `lorem()` method since v3.0.5 to generate lorem ipsum text.

### Template

If you want to add more kinds of sentences, just use the `.addTemplates()` method; it expects a list of sentence templates.
Each sentence template is an English sentence, containing placeholders that can be replaced with any alternative word.

For example:

```js
import {
  addTemplates
} from '@odczynflnpm/incidunt-quaerat-harum'

const templates = [
  '{{a_noun}} is {{a_noun}} from the right perspective',
  'the {{noun}} of {{a_noun}} becomes {{an_adjective}} {{noun}}'
]

addTemplates(templates)
```

Here are the available placeholders:

- `noun`
- `nouns`
- `a_noun`
- `adjective`
- `an_adjective`


### Lorem ipsum

Syntax:

```js
lorem() // generate a random phrase with length from 2 to 24 words of lorem ipsum
lorem(Number min) // set the minimum number of words
lorem(Number min, Number max)// set the minimum/maximum number of words
```

Example:

```js
import { lorem } from '@odczynflnpm/incidunt-quaerat-harum'

const phrase = lorem()
console.log(phrase) // => nisi blandit feugiat tempus imperdiet etiam eu mus augue
```

## Test

```bash
git clone https://github.com/odczynflnpm/incidunt-quaerat-harum.git
cd @odczynflnpm/incidunt-quaerat-harum
npm install
npm test
```

# License

The MIT License (MIT)
