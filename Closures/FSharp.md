**Closures in F#**

1.  Write the closure

Note the free variable in the AddSome function

```
let AddSome x =
    let y = 4
    let AddMore = fun z -> z + y
    AddMore x

```

2.  Run the closure

```
AddSome 1
AddSome 5
AddSome 12

```

