**JavaScript Callbacks**

Note:  JavaScript callbacks are one of the most abused aspect of JS that lead to spaghetti code.  In fact excessive callback usage is called Callback Hell.

1.  write a simple callback

```
var foo = function (x) {
    return x + 1;
}

var bar = function (y) {
    return y * 2;
}

foo(bar(5))

```

2.  write a function that can run an arbitrary callback

```
var bar = function (cb) {
    return cb()
}

```