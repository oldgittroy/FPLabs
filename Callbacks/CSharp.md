**C# Callback Lab**

1.  Write a function (myMethod) and send a callback (add1) to it.

```
public static int myMethod (Func<int, int> cb) 
{
    return cb(5);
}

public static void main()
{
    Func<int, int> add1 = (x) => x +1;
    int z = myMethod(add1);
}

```
2.  Try writing a callback function using strings

3.  Try a callback funciton passing a data structure
