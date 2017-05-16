**First Class Functions in F#**

fun x denotes a function in F#

1.  write a simple nested function 

```
let hw = 
    let echo = fun x -> x

    echo "Hello " |> echo "World!"

```