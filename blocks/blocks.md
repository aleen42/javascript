## Blocks [**Back**](./../README.md)

#### 1. Use braces

- To use braces with all multiple lines, but do not use when it's a single line.

```js
/**
 * bad
 */
if (test)
    return false;

/**
 * good
 */
if (test) return false;
if (test) {
    return false;
}

/**
 * bad
 */
function () { return false; }

/**
 * good
 */
function () {
    return false;
}
```

#### 2. Closing braces

- If using multi-line blocks with `if` and `else`, then put `else` on the same line of `if` block's closing braces.
- Eslint rules tags: [`brace-style`](http://eslint.org/docs/rules/brace-style.html)

```js
/**
 * bad
 */
if (test) {
}
else {
}

/**
 * good
 */
if (test) {
} else {
}
```
