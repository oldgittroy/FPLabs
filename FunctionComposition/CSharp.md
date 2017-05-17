**Function Composition in C#**


1.  Make a compose Func

```
var compose = Func<T, Func<int, int>, Func<int, int>, int> = (f, g, x) => 
    {
        return g(f(x));
    }

```
2.  Assuming there are two functions, add1 and add2, compose them

```
compose(add1, add2, 1);

```