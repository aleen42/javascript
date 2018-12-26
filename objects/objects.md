## Objects [**Back**](./../README.md)

#### 1. Use `{}`

- To use the literal syntax for object creation.
- Eslint rules tags: [`no-new-object`](http://eslint.org/docs/rules/no-new-object.html)

```js
/**
 * bad
 */
const item = new Object();

/**
 * good
 */
const item = {};
```

#### 2. Do not use `reserved words`
- If your code will be executed in browsers in script context, remember that it's not recommended to use reserved words as keys.

> the reason is that they won't work in IE8, but it's OK to use them in ES6 modules and server-side code.

```js
/**
 * bad
 */
const heros = {
    default: { name: 'aleen' },
    private: true
};

/**
 * good
 */
const heros = {
    defaults: { name: 'aleen' },
    hidden: true
};
```

- It's recommended that using readable synonyms(同義詞) in place of reserved words.

```js
/**
 * bad
 */
const heros = {
    class: 'alien'
};

/**
 * bad
 */
const heros = {
    klass: 'alien'
};

/**
 * good
 */
const heros = {
    type: 'alien'
};
```

#### 3. Use computed property names

- To use computed property names when creating objects with dynamic property names.

> the reason is that they allow you to define all the properties of an object in one place.

```js
function geyKey(k) {
    return `${k}`;
}


/**
 * bad
 */
const obj = {
    id: 5,
    name: 'Foshan'
};
obj[geyKey('enabled')] = true;

/**
 * good
 */
const obj = {
    id: 5,
    namd: 'Foshan',
    [geyKey('enabled')]: true
};
```

- *Notice that: computed properties are only supported by ECMAScript 6 (ES6). [**Browser Compatibility**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Browser_compatibility)*

#### 4. Use shorthand

- To use object method shorthand.
- Eslint rules tags: [`object-shorthand`](http://eslint.org/docs/rules/object-shorthand.html)

```js
/**
 * bad
 */
const atom = {
    value: 1,
    addValue: function(value) {
        return atom.value + value;
    }
};

/**
 * good
 */
const atom = {
    value: 1,
    addValue(value) {
        return atom.value + value;
    }
};
```

- To use property value shorthand.
- Eslint rules tags: [`object-shorthand`](http://eslint.org/docs/rules/object-shorthand.html)

```js
const aleenCheui = 'Aleen Cheui';

/**
 * bad
 */
const obj = {
    aleenCheui: aleenCheui
};

/**
 * good
 */
const obj = {
    aleenCheui
};
```

#### 5. Group shorthand

- To group your shorthand properties at the beginning of the object declaration.

> the reason is that it's easier to tell which properties are using the shorthand.

```js
const puiManCheui = 'PuiMan Cheui';
const syuJiZau = 'SyuJi Zau';

/**
 * bad
 */
const obj = {
    puiManCheui,
    episodeOne: 1,
    theSecond: 2,
    episodeThree: 3,
    SyujiZau,
    mayTheFourth: 4
};

/**
 * good
 */
const obj = {
    puiManCheui,
    SyujiZau,
    episodeOne: 1,
    theSecond: 2,
    episodeThree: 3,
    mayTheFourth: 4
};
```
