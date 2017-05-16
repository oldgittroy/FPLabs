**Currying in C#**

1.  Write a function that is not curried

```
Func<int, int, int> uncurry = (x, y) => x + y;

```
2.  Write a curried nested function

Watch those nested functions get jiggy!

```
Func<int, Func<int, int>> curry = x => y => x + y;

```

3.  Now bring it out

```
var add4 = curry(4);

int add2nums = add4(1);

```

