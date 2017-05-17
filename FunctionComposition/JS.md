**Function Composition in JavaScript**

1.  Make a compose function

```
function compose (f, g) {
    return function (x) {
        return g(f(x));
    }
}

```
2.  Write two functions, add1 and add2, to compose

3.  compose those functions

```
var c = compose(add1, add2);

```
