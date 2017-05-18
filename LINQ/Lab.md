**What are Combinator Libraries?**

1. Only use pure functions
2. Uses HoFs
3. Only use function application and previously defined combinators


LINQ is an example of a combinator library

* Pure Functions:  x=>x.prop
* HoFs:  Where(x=>x.prop)
* Function Application:  x.ToList()
* Previous Combinators: var x = foo + bar
* Expression Trees to generate the syntax


---

LINQ | Functional | What it does
---------|----------|---------
 Select | Map | moves data from one real to another
From | List/IEnumerable/[] | specifies a collection of data
 Where | Filter | pulls in a subset of data
 Aggregate/Sum | Reduce | 
 All | Every | 
 Any | Sort | 
 OrderBy | Sort | 
 SelectMany | Bind | 

 
