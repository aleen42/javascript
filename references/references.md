## References [**Back**](./../README.md)

#### 1. Use `const`
- To use `const` for all of your references, and avoid using `var`.
- Eslint rules tags: [`prefer-const`](http://eslint.org/docs/rules/prefer-const.html), [`no-const-assign`](http://eslint.org/docs/rules/no-const-assign.html)

> the reason is to ensure that you cannot reassign(重新訪問) references, which can lead to bugs and difficult to comprehend(理解) code.

```js
/**
 * bad 
 */
var a = 1;
var b = 2;

/**
 * good
 */
const a = 1;
const b = 2;
```

#### 2. Use `let`
- If you must reassign references, you can use `let` instead of `var`.
- Eslint rules tags: [`no-var`](http://eslint.org/docs/rules/no-var.html)

```js
/**
 * bad
 */
var count = 1;
count = count? count + 1 : count;
 
/**
 * good
 */
let count = 1;
count = count? count + 1 : count;
```

- *Notice that: both `const` and `let` are block-scoped(塊作用域).*

```js
{
    let a = 1;
    const b = 1;
}
console.log(a); /** ReferenceError  */
console.log(b); /** ReferenceError  */
```
