**Advanced Lab:  Unit Testing**

Functional programming using closures lends itself well to modularized code.  Unit testing of modularized code is much easier and more effective than testing code with lots of statements and conditionals.


How does one unit test a closure?  Currying makes testing very easy to do.

1.  Start with a simple Func

```
Func<int, int> add1 = (x) => x +1;

```
2.   Write a function to take the above as a callback

```
public static int myMethod (Func<int, int> cb) 
{
    return cb(5);
}

```
3.  Write a test harness using a currying Func

```
Func<int, Func<int, int>> harness = x => y => y(x); 

```
4.  Now write test code for the callback


```
var cb5 = harness(5);
int expected = cb5(1);

int actual = myMethod(cb5, 1);

Assert.AreEqual(actual, expected);

```
