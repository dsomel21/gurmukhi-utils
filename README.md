<!-- Do not modify README.md, instead modify README.hbs -->

# gurmukhi-utils

General utilities for working with Gurmukhi.

[![CircleCI](https://img.shields.io/circleci/project/github/ShabadOS/gurmukhi-utils.svg?style=for-the-badge)](https://circleci.com/gh/ShabadOS/gurmukhi-utils)
[![npm (scoped)](https://img.shields.io/npm/v/@shabados/gurmukhi-utils.svg?style=for-the-badge)](https://www.npmjs.com/package/@shabados/gurmukhi-utils)
[![David](https://img.shields.io/david/ShabadOS/gurmukhi-utils.svg?style=for-the-badge)](<>)
[![license](https://img.shields.io/github/license/ShabadOS/gurmukhi-utils.svg?style=for-the-badge)](<>)

## Usage

The library can be imported into Node as below:
```javascript
const { toUnicode, toAscii, firstLetters } = require('gurmukhi-utils')

toUnicode('Koj')    // Returns ਖੋਜ
toAscii('ਖੋਜ')       // Returns Koj
firstLetters('hir hir hir gunI')   // Returns hhhg
firstLetters('ਹਰਿ ਹਰਿ ਹਰਿ ਗੁਨੀ')      // Returns ਹਹਹਗ
```

Additionally, the package is available for web use via [unpkg CDN](https://unpkg.com/gurmukhi-utils).
```
<script src="https://unpkg.com/gurmukhi-utils"></script>
```

## Docs

* * *

## Functions

<dl>
<dt><a href="#firstLetters">firstLetters(line, [stripNukta])</a> ⇒ <code>String</code></dt>
<dd><p>Generates the first letters for a given ASCII or unicode Gurmukhi string.
By default, the function will transform letters with bindi to their simple equivalent,
for example, zaza to jaja (ਜ਼ =&gt; ਜ).</p>
</dd>
<dt><a href="#toUnicode">toUnicode(text)</a> ⇒ <code>String</code></dt>
<dd><p>Converts ASCII text used in the GurmukhiAkhar font to Unicode.</p>
</dd>
<dt><a href="#transliterate">transliterate(line)</a> ⇒ <code>String</code></dt>
<dd><p>Transliterates a line from ASCII Gurmukhi to english.
Currently supports the <code>,</code>, <code>;</code>, <code>.</code> vishraam characters.</p>
</dd>
</dl>

<a name="firstLetters"></a>

## firstLetters(line, [stripNukta]) ⇒ <code>String</code>
Generates the first letters for a given ASCII or unicode Gurmukhi string.
By default, the function will transform letters with bindi to their simple equivalent,
for example, zaza to jaja (ਜ਼ => ਜ).

**Kind**: global function  
**Returns**: <code>String</code> - The first letters of each word in the provided Gurmukhi line.  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| line | <code>String</code> |  | The line to generate the first letters for. |
| [stripNukta] | <code>Boolean</code> | <code>true</code> | If `true`, replaces letters pair bindi (such as ਜ਼) with their equivalent without the bindi (ਜ). Also replaces open oora with closed oora. |

**Example** *(Unicode first letters no pair bindi/nukta)*  
```js
firstLetters('ਗ਼ੈਰਿ ਹਮਦਿ ਹੱਕ ਨਿਆਇਦ ਬਰ ਜ਼ਬਾਨਮ ਹੀਚ ਗਾਹ') // => ਗਹਹਨਬਜਹਗ
```
**Example** *(Unicode first letters with pair bindi/nukta)*  
```js
firstLetters('ਗ਼ੈਰਿ ਹਮਦਿ ਹੱਕ ਨਿਆਇਦ ਬਰ ਜ਼ਬਾਨਮ ਹੀਚ ਗਾਹ') // => ਗ਼ਹਹਨਬਜ਼ਹਗ
```
**Example** *(ASCII first letters no pair bindi/nukta)*  
```js
firstLetters('ijs no ik®pw krih iqin nwmu rqnu pwieAw ]') // => jnkkqnrp
firstLetters('iZir&qym sMdUk drIXw AmIk ]') // => gsdA
```
**Example** *(ASCII first letters with pair bindi/nukta)*  
```js
firstLetters('iZir&qym sMdUk* drIXw AmIk* ]', false) // => Zsda
```
<a name="toUnicode"></a>

## toUnicode(text) ⇒ <code>String</code>
Converts ASCII text used in the GurmukhiAkhar font to Unicode.

**Kind**: global function  
**Returns**: <code>String</code> - A unicode representation of the provided ASCII Gurmukhi string.  

| Param | Type | Description |
| --- | --- | --- |
| text | <code>String</code> | The ASCII text to convert. |

<a name="transliterate"></a>

## transliterate(line) ⇒ <code>String</code>
Transliterates a line from ASCII Gurmukhi to english.
Currently supports the `,`, `;`, `.` vishraam characters.

**Kind**: global function  
**Returns**: <code>String</code> - The English transliteration of the provided Gurmukhi line.  

| Param | Type | Description |
| --- | --- | --- |
| line | <code>String</code> | The Gurmukhi ASCII line to transliterate. |

**Example**  
```js
transliterate('hukmI hukmu clwey rwhu ]') // => hukamee hukam chalaae raahu ||
```
**Example**  
```js
transliterate('BWfw Bwau AMimRqu iqqu Fwil ]') // => bhaa(n)ddaa bhaau anmrit tit ddaal ||
```

* * *

## Future

-   Unicode to ASCII
