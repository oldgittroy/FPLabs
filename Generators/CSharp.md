**Generators in C#**

implemented via the yield return keyword

1.  add yield return to a loop

```
for (int i=0; i< 5000; i++)
{
    yield return 1;
    yield return 2;
    yield return 3;
}

```
2.  put the for loop into a function and write another function to call it

