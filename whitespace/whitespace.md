## Whitespace [**Back**](./../README.md)

- Although it's recommended to set soft-warp as 2 spaces, I am still familiar with 4 spaces.
- Eslint rules tags: [`indent`](http://eslint.org/docs/rules/indent.html)
- My recommendation is to listen to your habits when setting `soft-tab`.

#### 1. One space

- Place 1 space before the leading brace.
- Eslint rules tags: [`space-before-blocks`](http://eslint.org/docs/rules/space-before-blocks.html)

```js
/**
 * bad
 */
function test(){
    console.log('test');
}

/**
 * good
 */
function test() {
    console.log('test');
}
```

- Place 1 space before the opening parenthesis in control statements (`if`, `while` etc.). Place no space before the argument list in function calls and declarations.
- Eslint rules tags: [`space-after-keywords`](http://eslint.org/docs/rules/space-after-keywords.html), [`space-before-keywords`](http://eslint.org/docs/rules/space-before-keywords.html)

```js
/**
 * bad
 */
if(isAleen) {
    console.log('Yo.');
}

/**
 * good
 */
if (isAleen) {
    console.log('Yo.');
}

/**
 * bad
 */
console.log ('Not good.');

/**
 * good
 */
console.log('Good.');
```

- Set off binary operators with one space, but not unary ones.
- Eslint rules tags: [`space-infix-ops`](http://eslint.org/docs/rules/space-infix-ops.html)

```js
/**
 * bad
 */
const x=y+5;

/**
 * good
 */
const x = y + 5;

/**
 * bad
 */
const x = y ++;

/**
 * good
 */
const x = y++;
```

#### 2. End files

- To end files with a single newline character.

```js
/**
 * bad
 */
(function (global) {
    /**
     * ...
     */
})(this);
```

```js
/**
 * bad
 */
(function (global) {
    /**
     * ...
     */
})(this);↵
↵
```

```js
/**
 * good
 */
(function (global) {
    /**
     * ...
     */
})(this);↵
```

#### 3. Chain Calling

- Use indentation(縮進) when making long method chains. And to use a leading dot, which emphasizes that the line is a method call, not a new statement.

```js
/**
 * bad
 */
$('#items').find('.selected').highlight().end().find('.open').updateCount();

/**
 * bad
 */
$('#items').
    find('.selected').
        highlight().
        end().
    find('.open').
        updateCount();
        
/**
 * good
 */
$('#items')
    .find('.selected')
        .highlight()
        .end()
    .find('.open')
        .updateCount();
```

#### 4. Leave a blank line after blocks and before the next statement

```js
/**
 * bad
 */
if (foo) {
    /**
     * ...
     */
}
console.log('test');

/**
 * good
 */
if (foo) {
    /**
     * ...
     */
}

console.log('test');
```

#### 5. Do not pad blocks with blank lines

- Eslint rules tags: [`padded-blocks`](http://eslint.org/docs/rules/padded-blocks.html)

```js
/**
 * bad
 */
if (foo) {
    
    console.log('test');
}

/**
 * bad
 */
if (foo) {
    console.log('test');

}

/**
 * good
 */
if (foo) {
    console.log('test');
}
```

#### 6. Do not add space inside brackets(方括號) and parentheses(圓括號), but add space inside braces(花括號).

- Eslint rules tags: [`space-in-parens`](http://eslint.org/docs/rules/space-in-parens.html), [`array-bracket-spacing`](http://eslint.org/docs/rules/array-bracket-spacing.html)

```js
/**
 * bad
 */
function bar( foo ) {
    /**
     * ...
     */
}

/**
 * good
 */
function bar(foo) {
    /**
     * ..
     */
}

/**
 * bad
 */
const items = [ 1, 2, 3 ];

/**
 * good
 */
const items = [1, 2, 3];

/**
 * bad
 */
const obj = {name: 'Aleen'};

/**
 * good
 */
const obj = { name: 'Aleen' };
```
