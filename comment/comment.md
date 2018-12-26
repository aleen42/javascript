## Comments [**Back**](./../README.md)

- use `/** ... */` for a single line
- use follow for multi-line:

```js
/**
 * this is a mutli-line comment
 */
```

#### 1. Function comments

- use `@param` to give comments for all the parameters of this function.
- use `@return` to give comments for what will be return of this function.

```js
/**
 * [initData: description]
 * @param  {[type]} data [description]
 * @return {[type]}      [description]
 */
function initData(data) {
    /**
     * ...
     */
}
```

#### 2. Control statements

- Comments of control statements such as `if`, `switch`, `for`, `while`.

```js
/** 
 * [if: description]
 * @param {[type]} test [description]
 */
if (test) {
    /**
     * ...
     */
}

/** 
 * [switch: description]
 * @param {[type]} test [description]
 */
switch (test) {
    case 'a':
        break;
}

/** 
 * [while: description]
 * @param {[type]} test [description]
 */
while (test) {
    /**
     * ..
     */
}

/** [for: description] */
for (len i = 0; i < 10; i++) {
    /**
     * ...
     */
}
```

#### 3. Helping comments

- `FIXME`: it's used to annotate(注釋) problems.
- `TODO`: it's used to annotate solutions to problems.

```js
class Aleen extends Hero {
    constructor() {
        super();
        
        // FIXME: shouldn't use a global here
        total = 0;
    }
}

class Aleen extends Hero {
    constructor() {
        super();
        
        // TODO: total should be configurable by an options param
        total = 0;
    }
}
```

#### 4. Header comments of files

```js
/***********************************************************************
 *                                                                   _
 *       _____  _                           ____  _                 |_|
 *      |  _  |/ \   ____  ____ __ ___     / ___\/ \   __   _  ____  _
 *      | |_| || |  / __ \/ __ \\ '_  \ _ / /    | |___\ \ | |/ __ \| |
 *      |  _  || |__. ___/. ___/| | | ||_|\ \___ |  _  | |_| |. ___/| |
 *      |_/ \_|\___/\____|\____||_| |_|    \____/|_| |_|_____|\____||_| 
 *                                                                      
 *      ================================================================
 *                 More than a coder, More than a designer              
 *      ================================================================
 *
 *
 *      - Document:     <file name>
 *      - Author:       <author name>
 *      - Description:  <description, which shoule be multi-line
 *                       when it's too long> 
 *      - Create Time:  <created time of this file>
 *      - Update Time:  <updated time of this file>
 *
 *
 **********************************************************************/
```
