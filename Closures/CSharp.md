**Closures in C#**

1.  Create a nested function with a free variable 

```
Func<int, int> AddStuff = (x) =>
{
    int y = 4;
    Func<int,int> AddOtherStuff  => x + y;

    return AddOtherStuff();
}

```
2.  Run the closure

```
AddStuff(1);

```
3.  Run it again

```
AddStuff(5);

```
the closure "remembers" that y =4 no matter how many times you use it.
