## Destructuring [**Back**](./../README.md)

- *Notice that: destructuring is only supported by ECMAScript 6 (ES6). [**Browser Compatibility**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Browser_compatibility)*

#### 1. Use object destructuring

- To use object destructuring when accessing and using multiple properties of an object.

> the reason is that destructuring can save from creating temporary references for those properties.

```js
/**
 * bad
 */
function getFullName(user) {
    const firstName = user.firstName;
    const lastName = user.lastName;
    
    return `${firstName} ${lastName}`;
}

/**
 * good
 */
function getFullName(user) {
    /**
     * you can change variables' name as follow:
     *  const {firstName: fName, lastName: lName} = user;
     * then you can return as follow:
     *  return fName + ' ' + lName; 
     */
    const {firstName, lastName} = user;
    
    return `${firstName} ${lastName}`;
}

/**
 * best
 */
function getFullName({firstName, lastName}) {
    return `${firstName} ${lastName}`;
}
```

- To use object destructuring for multiple return values, not array destructuring.

```js
/**
 * bad
 */
function processInput(input) {
    /**
     * then a miracle occurs
     */
    return [left, right, top, bottom];
}

/**
 * the caller needs to think about the order of return data
 */
const [left, __, top] = processInput(input);

/**
 * good
 */
function processInput(input) {
    /**
     * then a miracle occurs
     */
    return { left, right, top, bottom };
}

/**
 * the caller selects only the data they need
 */
const { left, top } = processInput(input);
```

#### 2. Use array destructuring

- To use array destructuring like object destructuring.

```js
const arr = [1, 2, 3, 4];

/**
 * bad
 */
const first = arr[0];
const second = arr[1];

/**
 * good
 */
const [first, second] = arr;
```
