**Closures in JavaScript**

1.  Write the closure, note the free variable

```
function AddStuff(x) {
    y = 4;
    function AddMoreStuff(z) {
        return z + y;
    } 

    return AddMoreStuff(x);
}

```

2.  Run the closure

