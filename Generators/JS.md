**Generators in JavaScript**

This only exists in ES6.  Use babel to transpile for older browsers.  May require a polyfill.

The yield keyword implements generators in JS

1.  Make a simple generator function

```
function foo* () {
    yield 1;
    yield;
    yield 2;
    yield 3;
}

```
2.  Make a function to call the generator function

```
function bar() {
    console.log(foo());
    console.log(foo());
    console.log(foo());
    console.log(foo());
}
```