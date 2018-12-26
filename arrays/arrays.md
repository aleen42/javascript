## Arrays [**Back**](./../README.md)

#### 1. Use `[]`

- To use literal syntax for array creation.
- Eslint rules tags: [`no-array-constructor`](http://eslint.org/docs/rules/no-array-constructor.html)

```js
/**
 * bad
 */
const items = new Array();

/**
 * good
 */
const items = [];
```

#### 2. Use `push()`

- To use Array#push instead of direct assignment to add items to an array.

```js
const arr = [];

/**
 * bad
 */
arr[arr.length] = 'aleen';

/**
 * good
 */
arr.push('aleen');
```

#### 3. Use spread operator `...`

- To use array spreads to copy arrays.

```js
/** 
 * bad
 */
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i++) {
    itemsCopy[i] = items[i]; 
}

/**
 * good
 */
const itemsCopy = [...items];
```

- *Notice that: spread operator is only supported by ECMAScript 6 (ES6). [**Browser Compatibility**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator#Browser_compatibility)*

#### 4. Use `from()`

- To convert an array-like object to an array, use Array#from.

```js
const foo = document.querySelectorAll('.foo');
const arr = Array.from(foo);
```
