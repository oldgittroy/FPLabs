**Currying in F#**

1.  Write uncurried function

```
let uncurry x y = 
    x + y

```

2.  Write curried version

```
let curry x = 
    let helper = 
        x + y
    helper

```