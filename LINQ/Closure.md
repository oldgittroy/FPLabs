**Closures in LINQ**


1.  Did you know you can use functions from C# classes in addition to Funcs?

```
public class Helper
{
    public string AddBrand(string item)
    {
        return "Troy's " + item;
    } 
}

```
2.  Make a function for awesomeness
```

var AddAwesome = Func<string, string> = x => "Awesome " + x;

```
3.  Compose the helper class method into the awesome function

```
Helper h = new Helper();

AddAwesome(h.AddBrand("Code"));

```

4.  Now lets make a bunch of items

```
var CoolThings = new string[]
{
    "Gobstopper",
    "Sweeties",
    "Chocolate"
};

```

5.  And finally use some LINQ action

```
var TroysAwesomeCoolThings = CoolThings.Select(x =>AddAwesome(h.AddBrand(x)));

```
