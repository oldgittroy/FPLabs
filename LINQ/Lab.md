**What are Combinator Libraries?**

1. Only use pure functions
2. Uses HoFs
3. Only use function application and previously defined combinators


_LINQ is an example of a combinator library_

* Pure Functions:  x=>x.prop
* HoFs:  Where(x=>x.prop)
* Function Application:  x.ToList()
* Previous Combinators: var x = foo + bar
* Expression Trees to generate the syntax


---

**Domain Specific Languages**

Describe what to do to the data, rather than what the data is.  OO = nouns, FP = verbs.


LINQ | Functional | What it does
---------|----------|---------
 Select | Map | moves data from one domain to another
From | List/IEnumerable/[] | specifies a collection of data
 Where | Filter | pulls in a subset of data
 Aggregate/Sum | Reduce | flattens a data structure
 All | Every | gets everything in a set
 Any | Sort | filters data in a set
 OrderBy | Sort | orders data in a set
 SelectMany | Bind | selects over multiple combinators

 ---

**LINQ example**

Looks like SQL but think of it as a nice way to combine expressions.

```
from products select product.ID 
where product.name == "Ultra Gobstopper"

```

---
** Advanced Labs**

* [Closure with LINQ](./Closure.md)
* [Catamorphisms with Select](./Catamorphism.md)
* [F# vs LINQ](./FSharp.md)

