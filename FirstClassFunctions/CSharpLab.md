**First Class Functions in C#**

1.  Try to make a funciton inside a function, inside a class

This should not compile, however C# 7 may allow nesting.

```
public class Arrgh 
{
    public void Rawr() 
    {
        console.write("Rawr!");

        public void Grr()
        {
            console.log("Grr!!!")
        }
        }
    }

}

```
In procedural programming, nesting functions are a great way to encapuslate if you don't have classes.

2.  Now, lets do it with Anonymous functions

```
var Rawr = ()=> 
{
    console.log("Rawr!!");

    return ()=>
    {
        console.log("Grr!!!");
    }

}

```
3.  Now with Func<T,U>

```
 Func<int, int> square (x) =>
 {
     return Func<int, int> (x) => 
     {
         return x * x;
     }
 } 

```

