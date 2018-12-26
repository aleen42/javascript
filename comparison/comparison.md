## Comparison Operators & Equality [**Back**](./../README.md)

- use `===` or `!==` rather than `==` or `!=`

#### 1. Conditional statements

- Conditional statements such as the `if` statement evaluate their expression using coericion(強制多態) with the `ToBoolean` abstract method and always follow these simple rules:
- Eslint rules tags: [`eqeqeq`](http://eslint.org/docs/rules/eqeqeq.html)
    - **Objects** evaluate to **true**.
    - **Undefined** evaluate to  **false**.
    - **Null** evaluate to **false**.
    - **Booleans** evaluate to  **the value of the boolean**
    - **Numbers** evaluate to **false** if **+0**, **-0**, or **Nan**, otherwise **true**
    - **Strings** evaluate to **false** if an empty string `''`, otherwise ** true**.

```js
if ([false]) {
    /**
     * true
     * because this is an object
     */
}
```

#### 2. Use shortcuts

```js
/**
 * bad
 */
if (name !== '') {
    /**
     * ...
     */
}

/**
 * good
 */
if (name) {
    /**
     * ...
     */
}

/**
 * bad
 */
if (collections.length > 0) {
    /**
     * ...
     */
}

/**
 * good
 */
if (collections.length) {
    /**
     * ...
     */
}
```

#### 3. More details

- [Truth Equality and JavaScript](http://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/#more-2108) by Angus Croll.
