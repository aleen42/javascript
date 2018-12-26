## Arrow Functions [**Back**](./../README.md)

#### 1. Use arrow functions notation

- To use arrow functions notation when you must use function expressions (as when passing an anonymous function).
- Eslint rules tags: [`prefer-arrow-callback`](http://eslint.org/docs/rules/prefer-arrow-callback.html), [`arrow-spacing`](http://eslint.org/docs/rules/arrow-spacing.html)

> Why? It creates a version of the function that executes in the context of `this`, which is usually what you want, and is a more concise syntax.
> Why not? If you have a fairly complicated function, you might move that logic out into its own function declaration.

```js
/**
 * bad
 */
[1, 2, 3].map(function (x) {
    const y = x + 1;
    return x * y;
});

/**
 * good
 */
[1, 2, 3].map((x) => {
    const y = x + 1;
    return x * y;
});
```

#### 2. Omit the braces(忽略大括號) and use the implicit(隱式) return

- If the function body only has a single expression, feel free to omit the braces and use the implicit return. Otherwise, use a `return` statement.
- Eslint rules tags: [`arrow-parens`](http://eslint.org/docs/rules/arrow-parens.html), [`arrow-body-style`](http://eslint.org/docs/rules/arrow-body-style.html)

> Why? Syntactic sugar(語法糖). It reads well when multiple functions are chained together.
> Why not? If you plan on returning an object.

```js
/**
 * good
 */
[1, 2, 3].map(number => `A string containing the ${number}.`);

/**
 * bad
 */
[1, 2, 3].map(number => {
    const nextNumber = number + 1;
    `A string containing the ${nextNumber}.`
});

/**
 * good
 */
[1, 2, 3].map(number => {
    const nextNumber = number + 1;
    return `A string containing the ${nextNumber}.`
});
```

- If the expression spans over multiple lines, wrap it in parentheses(圓括號) for better readability.

```js
/**
 * bad
 */
[1, 2, 3].map(number => 'As time went by, the string containing the ' +
    `${number} became much longer. So we needed to break it over multiple ` +
    'lines.'
);

/**
 * good
 */
[1, 2, 3].map(number => (
    `As time went by, the string containing the ${number} became much
    longer. So we needed to break it over multiple lines.`
));
```

#### 3. Omit the parentheses(忽略圓括號)

- If your function only takes a single argument, feel free to omit the parentheses.
- Eslint rules tags: [`arrow-parens`](http://eslint.org/docs/rules/arrow-parens.html)

```js
/**
 * good
 */
[1, 2, 3].map(x => x * x);
[1, 2, 3].map((x, y) => x + y);
```
