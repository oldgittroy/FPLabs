**Function Composition in F#**

1.  define the operator

```
let (>>) f g x = g ( f(x) )

```
2.  Set up functoins to componse

```
let add1 x = x + 1
let add2 x = x + 2

```
3.  Basic composition

```
let comp = add1 >> add2

```
4.  run the composition

```
comp 1

```



