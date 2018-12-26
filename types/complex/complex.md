## Complex [**Back**](./../types.md)

- When accessing a complex type, you should work on a reference to its value.
    - `object`
    - `array`
    - `function`

```js
const foo = [1, 2];
const bar = foo;                /** array type  */

bar[0] = 9;

console.log(foo[0], bar[0]);    /** => 9, 9     */
```
