**Catamorphisms in LINQ**

Catamorphisms generalize folds of lists to arbitrary algebraic data types.

---
For a more practical and applied context let's start with folds.  A fold flattens the dimensions of a data structure.  In JavaScript folds are implemented with the .reduce() function.  LINQ implements folds using the Aggregate expression.


1.  start with some structured data

```
List<int> numnum = new List<int>{1, 2, 3};

```
2.  Flatten the data using Aggregate

```
int product = numnum.Aggregate((x,y)=>x * y);

```

See how the List of ints is compacted into a single number?

3.  Look at the callback passed into Aggregate

```
(x,y) => x * y

```

The first parameter of that function is a result that is tallyed every time the callback is invoked.  The second parameter is the current item.

4.  Make a counter

```
int counter = numnum.Aggregate((result,item)=> result++);

```

5.  Make a string from an array of strings

```
System.Text.StringBuilder sb = new System.Text.StringBuilder();

string poem = ArrayOfLines.Aggregate((result, item)=> sb.AppendLine(item));

```

---
Folds are extremely useful.  Now lets look at the generalization of folds called catamorphisms or maps.  Catamorphisms do not flatten data structures but they return a new data structure of the same size.  In JavaScript catamorphisms are implemented with the map() function.  LINQ implements catamorphisms with the Select expression.


1.  Do a simple mapping

```
var foo = new 
{
    new Customer() {id = 1, Name="John"},
    new Customer() {id = 2, Name = "Martha"}
};

var SameLastName = foo.Select(x => x.Name += " Jones");

```

---

However all catamorphisms are still mathematically just a type of fold.  so lets try the catamorphism above as a fold.


```
var SameLastName = foo.Aggregate((result, item)=>{result.Name += "Jones"});

```

