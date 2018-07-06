## Accessors [**Back**](./../README.md)

- Accessors functions for properties are not required.

#### 1. Use `getVal()` and `setVal(val)`

```js
/**
 * bad
 */
dragon.age();
dragon.age(25);

/**
 * good
 */
dragon.getAge();
dragon.setAge(25);
```

#### 2. Use `isVal()` or `hasVal()`

- To use `isVal()` or `hasVal()` when the property is a `boolean`.

```js
/**
 * bad
 */
if (!dragon.age()) {
}

/**
 * good
 */
if (!dragon.hasAge()) {
}
```

#### 3. Use `get()` and `set()`

- It's ok to create `get()` and `set()`, but be consistent.

```js
class Aleen {
    constructor(options = {}) {
        const lightsaber = options.lightsaber || 'blue';
        this.set('lightsaber', lightsaber);
    }
    
    set(key, val) {
        this[key] = val;
    }
    
    get(key) {
        return this[key];
    }
}
```
