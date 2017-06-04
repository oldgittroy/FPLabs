**F#**

F# is a bit like an entire language which works like LINQ.


1.  Try a couple of operators

```
let (select) x y = map(x,y)
let (aggregate) x y = fold(x, y)

```
2.  use those operators

```
let dat = [0..10]
let doubler = 
    fun x -> x * 2
let doubles = data.select doubler

```
LINQ in F#.  Also we did an example catamorphism


3.  Do a closure

```
let tripler = 
    fun x y -> x + y
let triples  = doubles.tripler dat

```

