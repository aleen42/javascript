## Commas & Semicolons [**Back**](./../README.md)

### 1. Commas

- Add one space after each commas.
- It's recommended that adding commas of each properties, buy I'm familiar with the style that last property does not have the commas.
- Eslint rules tags: [`comma-dangle`](http://eslint.org/docs/rules/comma-dangle.html)

```js
/** bad */
const items = [1,2,3];

/** good */
const items = [1, 2, 3];

/** recommended */
const items = [
    1,
    2,
    3,
];

/** bad */
const obj = {
    name: 'Aleen',
    age: '22'
};

/** recommended */
const obj = {
    name: 'Aleen',
    age: '22',
};
```

### 2. Semicolons

- Add semicolons after each statements.
- Eslint rules tags: [`semi`](http://eslint.org/docs/rules/semi.html)

```js
/** bad */
const i = 1

/** good */
const i = 1;
```
