**Using Bind in C#**

I.  Extension Methods

1.  Start with a static class

```
public static class Meh
{

}

```
2.  Add a static method with the this keyword in its parameter list

```
public static class Meh
{
    public static int Count(this Thingie int[])
    {
        return Thingie.length;
    }
}

```

3.  Use Generics to handle multiple classes

```
public static class Meh
{
    public static int Count(this Thingie <T>[])
    {
        return Thingie.Length;
    }
}

```

4.  Use the extension method

```
using Meh;

public class DoStuff
{
    int[] foo = new int[]{1, 2,3, 4, 5};
    console.writeline(foo.Count());

    double[] bar = new double[] {1.0,2.0,3.0,4.0,5.0};
    console.writeline(bar.Count());
}

```
---

II.  Funky interfaces

1.  Make the interface

```
interface IMeh
{
    int Count(<T> Thingie);
}

```

2.  Implement the Interface

```
public class Meh
{
    public int Count(<T> Thingie)
    {
        return Thingie.Length;
    }
}

```

3.  Use the interface

```
public class DoStuff: IMeh
{
    Meh m = new Meh();

    int[] foo = new int[]{1, 2,3, 4, 5};
    console.writeline(m.Count(foo));

    double[] bar = new double[] {1.0,2.0,3.0,4.0,5.0};
    console.writeline(m.Count(bar));
}

```
Far from ideal.  Lets try making a bind function


4.  Make a binding method

```
public class Binder<T>
{
    public Binder<T> bind<T>(Func<T, Binder<T>> func)
    {

    }
}

```

5.  Add binding to the DoStuff class

```
m.Count(foo)
.bind(x => x++)
.bind(y => y /2);

```

Not as useful as an extension method yet but its a direction.


---
III.  LINQ SelectMany

1.  Use SelectMany to query child collections.

```
List<int> list = new List<int>
{
    1,
    2,
    3
}

var add3 = x => x + 3;

var ChildQuery = list.SelectMany(add3);

```

2.  Try it with some tuples

```
var t1 = new {Name ="foo", Values = new int[]{1, 2,3 ,4, 5}};
var t2 = new {Name="bar", Values= new double[] {1.0, 2.0, 3.0, 4.0, 5.0}};

var data = new [] {t1, t2};

var GetEven = data.SelectMany(x => x/2 > 1);

```

