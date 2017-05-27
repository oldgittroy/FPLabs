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

3.  Replace if code with function composition


Start with the conditional statement

```
if (x > 1) 
{
    return true;
}

```

Recode the condition as a Func

```
Func<bool, int> gt1 = x => x > 1;

```
Actually this is a C# predicate

```
Predicate<int> gt1 = x => x > 1;

```

Now create a function composition from add1 with the gt1 predicate:

```
compose(add1, gt1, 1);

```
The result is a type exception, just like an unimplemented polymorphic type.  so lets implement that type by casting.

```
Func<int, bool> getint = x => (int)x;

```

And finally, the if is completely gone.

```
int seed = 1;
compose(add1, compose(gt1,getint,seed), seed);

```

The potentially difficult to test if statement is now replaced with individually testable functions.  
