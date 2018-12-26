## Naming [**Back**](./../README.md)

#### 1. Use camelcase

- To use camelCase when naming `objects`, `functions` and `instances`.
- Eslint rules tags: [`camelcase`](http://eslint.org/docs/rules/camelcase.html)

```js
const thisIsAnObject = {};
function helloAleen() {}
```

#### 2. Use pascalcase

- To use PascalCase when naming `constructors` or `classes`.

```js
class PuiManCheui {
    constructor(options) {
        this.name = options.name;
    }
}

const good = new PuiManCheui({
    name: 'Aleen',
});
```

#### 3. Use a leading underscore `_`

- To use a leading underscore `_` when naming private properties.
- Eslint rules tags: [`no-underscore-dangle`](http://eslint.org/docs/rules/no-underscore-dangle.html)

```js
this._firstName = 'PuiMan';
```

#### 4. Do not save references to `this`

- Do not save references to `this`, and use arrow functions or Function#bind instead.

```js
/**
 * bad
 */
function foo() {
    const self = this;
    return function() {
        console.log(self);
    };
}

/**
 * good
 */
function foo() {
    return () => {
        console.log(this);
    };
}

function foo() {
    function returnFunc() {
        console.log(this);
    }
    
    return returnFunc.bind(this);
}
```

#### 5. Name the file with the class name

```js
class CheckBox {
  /**
   * ...
   */
}
export default CheckBox;

/**
 * bad
 */
import CheckBox from './checkBox';
import CheckBox from './check_box';

/**
 * good
 */
import CheckBox from './CheckBox';
```

- use camlcase to export a `function`
- use pascalcase to export a `singleton` / `function library` / `bare object`.

```js
function makeStyleGuide() {
}

export default makeStyleGuide;

const StyleGuide = {
    es6: {
    }
};

export default StyleGuide;
```
