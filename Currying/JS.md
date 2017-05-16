**Currying in JavaScript**

JavaScript currying occurs via nested functions

1.  Write a non-curried function first

```
function noncurry(x, y,z) {
    return x + y + z;
}

```
2.  Factor into two functions

```
function littleCurry(y,z) {
    return function (x) {
        return x + y + z;
    }
}

```

Of course the value of x can be set as a free variable within the closure.

3.  Factor all the way down
```

function allCurry(z) {
    return function(y){
        return function(x){
             return x + y + z;
        }
    }
}
```

