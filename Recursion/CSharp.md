Recursion in C#

1.  Write a simple recursive function

```
public static int recurse(int level)
{
    if (level < 4)
    {
        level = recurse(level++);
    } 

    return level;
}

public static void main()
{
    int z = recurse(0);
}
```