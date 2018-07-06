## String [**Back**](./../README.md)

#### 1. Use single qutoes for string

- To use single quotes `''` for strings.
- Eslint rules tags: [`quotes`](http://eslint.org/docs/rules/quotes.html)

```js
/**
 * bad
 */
const name = "PuiMan Cheui";

/**
 * good
 */
const name = 'PuiMan Cheui';
```

#### 2. Multiple lines when too many characters

- Strings that cause the line to go over **100** characters should be written across multiple lines using string concatenation.
- *Note that: if overused, long strings with concatenation could impact performance. [jsPerf](http://jsperf.com/ya-string-concat) & [Discussion](https://github.com/airbnb/javascript/issues/40).*

```js
/**
 * bad
 */
const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';

/**
 * bad
 */
const errorMessage = 'This is a super long error that was thrown because \
of Batman. When you stop to think about how Batman had anything to do \
with this, you would get nowhere \
fast.';

/**
 * good
 */
const errorMessage = 'This is a super long error that was thrown because ' +
  'of Batman. When you stop to think about how Batman had anything to do ' +
  'with this, you would get nowhere fast.';
  
/**
 * you can also use template string
 */
const errorMessage = `This is a super long error that was thrown because 
  of Batman. When you stop to think about how Batman had anything to do 
  with this, you would get nowhere fast.`;
```

#### 3. Use template strings

- When programmatically building up strings, use template strings instead of concatenation.

> the reason is that template strings give you a readable, concise(簡練的) syntax with proper newlines and string interpolation(內插) features.

```js
/**
 * bad
 */
function sayHi(name) {
    return 'How are you, ' + name + '?';
}

/**
 * bad
 */
function sayHi(name) {
    return ['How are you, ', name, '?'].join();
}

/**
 * good
 */
function sayHi(name) {
    return `How are you, ${name}?`;
}
```

- *Notice that: template strings are only supported by ECMAScript 6 (ES6). [**Browser Compatibility**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings#Browser_compatibility)*

#### 4. Do not use `eval()`

- It's not recommended to use `eval()` on a string, cause it will open too many vulnerabilities(弱點).
