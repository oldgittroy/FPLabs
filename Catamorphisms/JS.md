**Catamorphisms in JavaScript**

JavaScript has a map function that works on arrays

1.  make an array of things to map

```
var stuff = [1,2,3,4,5,6,7,8,9,10];

```
2.  Make a function and pass it into map

```
function add1(x) {
    return x + 1;
}

stuff.map(add1);

```
