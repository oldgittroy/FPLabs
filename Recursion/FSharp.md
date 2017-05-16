**Recursion in F#**

1.  Write a nested helper function

```
let recurse max =    
    let rec sum n acc = 
        match n with
        | 0 -> acc
        | _ -> sum (n-1) (n + acc)
    sum max 0

```            

2.  Test the recursive function

```
recurse 10

```
3.  Try rewriting the C# recursive example in F#

While F# will do recursion, it also has a recursive type that we will look at later.



