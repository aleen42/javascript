## Hoisted [**Back**](./../README.md)

#### 1. Instruction

- `var` declarations get hoisted to the top of their scope, but their assignment does not.
- `const` and `let` declarations also get hoisted to the top of their scope, but their references do not.
- `const` and `let` declarations are blessed with(享有) a new concept called [*Temporal Dead Zones (TDZ)*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_dead_zone_and_errors_with_let).
- It's important to know that `typeof` is no longer safe.

```js
/**
 * var
 */
{
    console.log(foo);   /** undefined       */
    var foo = 2;
}

/**
 * let and const
 */
{
    len foo;
    console.log(foo);   /** undefined       */
    foo = 2;
}
 
{
    /**
     * In ECMAScript 2015, let will hoist the variable
     * to the top of the block. However, referencing the 
     * variable in the block before the variable declaration 
     * results in a ReferenceError. 
     * The variable is in a "temporal dead zone"
     * from the start of the block until the
     * declaration is processed.
     */
    console.log(foo);   /** ReferenceError  */
    const foo = 2;
}
```

#### 2. Function expressions

- Anonymous function expressions hoist their variable name, but not the function assignment.

```js
function example() {
    console.log(anonymous);     /** undefined                   */
    
    anonymous();                /** TypeError, not a function   */
    
    var anonymous = function() {
        console.log('anonymous function expression');
    };
}
```

- Named function expressions hoist the variable name, not the function name or the function body.

```js
function example() {
    console.log(named);     /** undefined                       */
    
    named();                /** TypeError, not a function       */
    
    f();                    /** ReferenceError, f not defined   */
    
    var named = function f() {
        console.log('f');
    };
}

function example() {
    console.log(named);     /** undefined                       */
    
    named();                /** TypeError, not a function       */
    
    var named = function named() {
        console.log('named');
    };
}
```

#### 3. Function declarations

- Function declarations hoist both the name and the function body.

```js
function example() {
    f();    /** => f    */
    
    function f() {
        console.log('f');
    }
}
```

#### 4. More details

- [JavaScript Scoping & Hoisting](http://www.adequatelygood.com/2010/2/JavaScript-Scoping-and-Hoisting/) by [Ben Cherry](http://www.adequatelygood.com/).
