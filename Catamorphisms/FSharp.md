**Catamorphisms in F#**

Map is very straightforward in F#

1.  Make a list of elements

```
let stuff = [0...10]

```
2.  Make a mapping function and call map with it

```
let add1 x = x + 1

let plusOne = stuff.map add1

```
Easy as pie