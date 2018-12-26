## Iterators and Generators [**Back**](./../README.md)

#### 1. Do not use iterators

- Do not use iterators. Prefer JavaScript's higher-order functions like `map()` and `reduce()` instead of loops like `for-of`.
- Eslint rules tags: [`no-interator`](http://eslint.org/docs/rules/no-iterator.html)

> the reason is that this enforces(強制執行) our immutable(永恆不變的) rules. Dealing with pure functions that return values is easier to reason about than side-effects.

```js
const numbers = [1, 2, 3, 4, 5];

/**
 * bad
 */
let sum = 0;
for (let num of numbers) {
    sum += num;
}

/**
 * good
 */
let sum = 0;
number.foreach(num => sum += num);

/**
 * best (use the funtional force)
 * arr.reduce(callback,[initialValue])
 * callback: function(previousValue, currentValue, index, array)
 * initialValue: the previousValue when first call the callback function
 */
const sum = numbers.reduce((total, num) => total += num, 0);
```

#### 2. Do not use generators for now (reserved)

> the reason is that generators cannot be transpiled well to ES5.
