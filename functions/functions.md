## Functions [**Back**](./../README.md)

#### 1. Use function declarations

- To use function declarations instead of function expressions.

> the reason is that function declarations are named, so they are easier to identify in call stacks. Also, the whole body of a function declarations is hoisted(變量聲明提升), whereas(然而) only the reference of a function expression is hoisted. This rule makes it possible to always use [*Arrow Functions*](./../arrowFunctions/arrowFunctions.md) in place of function expressions.

```js
/**
 * bad
 */
const foo = function() {
};

/**
 * good
 */
const foo() {
}
```

- Use arrow functions in place of function expressions as follow:

```js
/**
 * immediately-invoked function expression (IIFE)
 */
(() => {
    console.log('Welcome to the Internet. Please follow me.');
})();
```

- *Notice that: arrow functions are only supported by ECMAScript 6 (ES6). [**Browser Compatibility**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions#Browser_compatibility)*

#### 2. Do not declare functions in a non-function block

- Never declare a function in a non-function block (if, while, etc). Assign the function to a variable instead. Browsers will allow you to do it, but they all interpret it differently, which is bad news bears.
- *Note: ECMA-262 defines a block as a list of statements. A function declaration is not a statement. [**Read ECMA-262's note on this issue**](http://www.ecma-international.org/publications/files/ECMA-ST/Ecma-262.pdf#page=97).*

```js
/**
 * bad
 */
if (currentUser) {
    function test() {
        console.log('Nope.');
    }
}

/**
 * good
 */
if (currentUser) {
    test = () => {
        console.log('Yup.');
    };
}
```

#### 3. Never name a parameter `arguments`

- Never name a parameter `arguments`, because this will take precedence(優先級) over the `arguments` object that is given to every function scope.

```js
/**
 * bad
 */
function nope(name, options, arguments) {
    /**
     *  ...stuff...
     */
}

/**
 * good
 */
function yup(name, options, args) {
    /**
     *  ...stuff...
     */
}
```

- Also, never use `arguments`, opt to use rest syntax `...` instead.

> the reason is that `...` is explicit about which arguments you want pulled. Plus rest arguments are a real Array and not Array-like like `arguments`.

```js
/**
 * bad
 */
function concatenateAll() {
    const args = Array.prototype.slice.all(arguments);
    return args.join(' ');
}

/**
 * good
 */
function concatenateAll(...args) {
    return args.join(' ');
}
```

#### 4. Use default parameter syntax

- To use default parameter syntax rather than mutating(使...變異) function arguments.

```js
/**
 * really bad
 */
function handleThings(opts) {
    /**
     * No! We shouldn't mutate function arguments.
     * Double bad: if opts is false it'll be set to an object which may
     * be what you want but it can introduce subtle bugs.
     */
    opts = opts || {};
    
    /**
     * ...
     */
}

/**
 * still bad
 */
function handleThings(opts) {
    if (opts === void 0) {
        opts = {};
    }
    
    /**
     * ...
     */
}

/**
 * good
 */
function handleThings(opts = {}) {
    /**
     * ...
     */
}
```

- Avoid side effects with default parameters.

```js
var b = 1;

/**
 * bad
 */
function count(a = b++) {
    console.log(a);
}

count();    /** => 1    */
count();    /** => 2    */
count(3);   /** => 3    
             * when a is assigned,
             * b will not increase itself
             */
count();    /** => 3    */
```

- Always put default parameters last.

```js
/**
 * bad
 */
function handleThings(opts = {}, name) {
    /**
     * ...
     */
}

/**
 * good
 */
function handleThings(name, opts = {}) {
    /**
     * ...
     */
}
```

#### 5. Never use the `Function` constructor

- Never use the `Function` constructor to create a new function.

> the reason like using `eval()` on a string, is that creating a function in this way will open vulnerabilities.

```js
/**
 * bad
 */
var add = new Function('a', 'b', 'return a + b');

/**
 * still bad
 */
var subtract = Function('a', 'b', 'return a - b');
```

#### 6. Spacing

- To spacing in a function signature.

> Consistency is good, and you shouldn’t have to add or remove a space when adding or removing a name.

```js
/**
 * bad
 */
const f = function(){};
const g = function (){};
const h = function() {};

/**
 * good
 */
const x = function () {};   /** 
                             * of course it's recommended
                             * that using function x() {}
                             */
const y = function a() {};
```

#### 7. Never mutate parameters

- Do not to manipulating objects passed in as parameters to mutate them.
- Eslint rules tags: [`no-param-reassign`](http://eslint.org/docs/rules/no-param-reassign.html)

> the reason is that this can cause unwanted variable side effects in the original caller.

```js
/**
 * bad
 */
function change(obj) {
    obj.key = 1;
}

/**
 * good
 */
function change(obj) {
    const key = Object.prototype.hasOwnProperty.call(obj, 'key') ? obj.key : 1;
}
```

- Do not reassign parameters.
- Eslint rules tags: [`no-param-reassign`](http://eslint.org/docs/rules/no-param-reassign.html)

> the reason is that reassigning parameters can lead to unexpected behavior, especially when accessing the arguments object. It can also cause optimization issues, especially in V8.

```js
/**
 * bad
 */
function change(a) {
    a = 1;
}

function change(a) {
    if (!a) {
        a = 1;
    }
}

/**
 * good
 */
function change(a) {
    const b = a || 1;
}

function change(a = 1) {

}
```
