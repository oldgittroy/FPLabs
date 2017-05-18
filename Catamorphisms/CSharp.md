**Catamorphisms in C#**

Catamorphisms apply a mapping function f to items in a list of data.  

1.  One method of emulating the map() function in C# uses generators

```
public List<int> map(List<int> list, Func<T, U> f)
for(var i=0; i<list.count; i++)
{
    yield f(list[i]);
}

```
This code probably does not work but its there if you need it.

2.  The best way to implement map() in C# is through LINQ using the select operator

```
Func<int, int> add = x => x + 1;

var list 2 = list.select(add) 

```
