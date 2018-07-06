## Properties [**Back**](./../README.md)

#### 1. Use dot notation

- To use dot notation when accessing properties.
- Eslint rules tags: [`dot-notation`](http://eslint.org/docs/rules/dot-notation.html)

```js
const Aleen = {
    name: 'PuiMan Cheui',
    age: '22'
};

/**
 * bad
 */
const name = Aleen['name'];

/**
 * good
 */
const name = Aleen.name;
```

#### 2. Use subscript notation `[]`

- To use subscript notation `[]` when accessing properties with a variable.

```js
const Aleen = {
    name: 'PuiMan Cheui',
    age: '22'
};

function getProperty(prop) {
    return Aleen[prop];
}

const name = getProperty('name');
```
