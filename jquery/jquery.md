## jQuery [**Back**](./../README.md)

#### 1. Prefix `$`

- Prefix jQuery objects variables with `$`

```js
/**
 * bad
 */
const sidebar = $('.sidebar');

/**
 * good
 */
const $sidebar = $('.sidebar');
```

#### 2. Cache jQuery object

```js
/**
 * bad
 */
function setSidebar() {
    $('.sidebar').hide();
    
    /**
     * ...
     */
    
    $('.sidebar').css({
        'background-color': 'blue'
    });
}

/**
 * good
 */
function setSidebar() {
    const $sidebar = $('.sidebar');
    $sidebar.hide();
    
    /**
     * ...
     */
    
    $sidebar.css({
        'background-color': 'blue'
    });
}
```

#### 3. Use Cascading or parent > child

- To use Cascading `$('.sidebar ul')` or parent > child `$('.sidebar > ul')`, which named **context selector**

```js
$('.sidebar ul').hide();

$('.sidebar > ul').hide();

$sidebar = $('.sidebar');
$sidebar.find('ul').hide();
```

#### 4. Performance of different selectors

- The performance testing [jsPerf](http://jsperf.com/jquery-find-vs-context-sel/16) between `.find()`, `context selector` and `non-context selector`. 

- **Testing in Chrome 47.0.2526.106 32-bit on Windows NT 10.0 64-bit**

Type|Statements|Results(*Opts/sec*
:---:|:---:|:---:
`find` method (node context)|```const has = $(artical).find('ins').length > 0 ? true : false```|203,913 ± 1.12% (**fastest**)
context node|```const has = $('ins', article).length > 0 ? true : false;```|169,866 ± 10.33% (17% slower)
context jQuery[0]|```const has = $('ins', $article[0]).length > 0 ? true : false;```|154,641 ± 6.12% (24% slower)
cascade|```const has = $('article ins').length > 0 ? true : false;```|18,615 ± 1.80% (91% slower)
'parent > child' selector|```const has = $('article > ins').length > 0 ? true : false;```|15,888 ± 5.97% (92% slower)
context jQuery|```const has = $('ins', $article).length > 0 ? true : false;```| 10,120 ± 4.92% (95% slower)
`find` method (jQuery context)|```const has = $($article).find('ins').length > 0 ? true : false;```|9,599 ± 1.84% (95% slower)
context (no cache)|```const has = $('ins', 'article').length > 0 ? true : false;```|9,156 ± 4.45% (96% slower)
select and find|```const has = $('article').find('ins').length > 0 ? true : false;```|7,046 ± 8.12% (97% **slowest**)

- **Testing in Firefox 42.0 32-bit on Windows NT 10.0 64-bit**

Type|Statements|Results(*Opts/sec*
:---:|:---:|:---:
`find` method (node context)|```const has = $(artical).find('ins').length > 0 ? true : false```|132,743 ± 8.18% (**fastest**)
context jQuery[0]|```const has = $('ins', $article[0]).length > 0 ? true : false;```|123,678 ± 2.04% (**fastest**)
context node|```const has = $('ins', article).length > 0 ? true : false;```|108,953 ± 5.23% (18% slower)
cascade|```const has = $('article ins').length > 0 ? true : false;```|17,027 ± 3.86% (87% slower)
'parent > child' selector|```const has = $('article > ins').length > 0 ? true : false;```|15,982 ± 7.53% (88% slower)
context jQuery|```const has = $('ins', $article).length > 0 ? true : false;```| 6,307 ± 2.37% (95% slower)
`find` method (jQuery context)|```const has = $($article).find('ins').length > 0 ? true : false;```|5,433 ± 5.18% (96% slower)
select and find|```const has = $('article').find('ins').length > 0 ? true : false;```|5,268 ± 5.23% (96% slower)
context (no cache)|```const has = $('ins', 'article').length > 0 ? true : false;```|4,727 ± 7.55% (96% **slowest**)
