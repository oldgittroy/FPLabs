**Immutability Lab**

Expressions, not statements.  Math libraries are an example of things that should be pure functions.  1 + 1 better be 2.

**C# static methods**

1. Create a static class for math

```
public static class MyMath 
{
    
}

```
2. Create a static method
We are not worrying about generics yet.  Just go with it.

```
public static int Add(int val1, int val2) => 
{
    return val1 + val2;
}

```

3. Create a static method for adding strings

4. Write a unit test to show that 1 + 1 is 2

5.  Write a unit test for the string addition method


**F# functions**

1. Find a big stick
2. Find F# developers who use the mutable keyword
3. Smack them with the stick

seriously though, lets try a few functions in F#


1. Go to the cheat site
[link](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/fsharp-in-60-seconds.html)

2. Write a simple function

```
let myadd x y = x + y

```

3. Test the myadd function with numbers

```
myadd 1 1

```
4.  Test the myadd function with strings

```
myadd "Hello" " world!"

```


**JS functions**

JavaScript functions are not intrinsically pure.  However they can be coded to work that way.

For example, a function that can be called without making use of its return value is not pure.  Pure functions take a parameter and return a value without changing the state of any parameters.

1.  Make an ES5 style function

```
var myadd = function (x,y) {
    return x + y;
}

```

