**First Class Functions in JavaScript**

1.  Put a function inside a function

```
var foo = function () {
    var hello = "Hello"

    return function () {
        return hello + " World!"
    }
}

```
2.  In JavaScript objects {} are functions, and vice versa

```
var foo = function () {
    return {
        return hello + "World!"
    }
}

```