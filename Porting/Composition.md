**Use Higher Order Functions for Inheritance and Polymorphism**

1. Create some validation rules to use to validate form data

```
Predicate<string> NonNullString = x => x != null;
Predicate<string> NonEmptyString = x => x != "";
Predicate<string> NonZeroString = x => x.Length > 0;

```
2.  On your own, make a few more rules using Regex

3.  Start a string validation method using the predicates

```

Func<ArrayList<string>,string> ValidateName = name =>
{
    ArrayList<string> msg = new ArrayList<string>();

    if (!NonNullString(name) ||
    !NonEmptyString(name) ||
    !NonZeroString(name))
    {
        msg.push("Invalid name.")
    }
    
}

```

4.  Consolidate all the potential ifs into a comparitor

```
Func<string, Predicate<string>, string,string> comparitor = predicate, data, err => 
{
    if (predicate(data)) return err;
}

```

5.  How to use the comparitor

```
comparitor(NonNullString, name, "Name cannot be null");
comparitor(NonEmptyString, name, "Name cannot be blank");
comparitor(NonZeroString, name, "Name cannot be blank");

```

6.  Wouldn't it be nice to show different kinds of errors in the same function?

Bring out the tuples!

```
ArrayList<Tuple<Predicate<T>, string>> stack = ArrayList<Tuple<Predicate<T>, string>>();

stack.Add(new Tuple<Predicate<T>, string>(NonNullString,"Name cannot be null"));

stack.Add(new Tuple<Predicate<T>, string>(NonEmptyString,"Name cannot be blank"));

stack.Add(new Tuple<Predicate<T>, string>(NonZeroString,"Name cannot be blank"));

```

7.  Validate multiple rules using the tuples

```
Func<ArrayList<string>,ArrayList<Tuple<Predicate<T>, string>>> ValidateName = comps, name =>
{
    foreach(var comp in comps)
    {
        comparitor(comp.Item1, name, comp.Item2);
    }
    
}

```

Although this is for the next section, turn that if into a catamorphism:

```
Func<ArrayList<string>,ArrayList<Tuple<Predicate<T>, string>>> ValidateName = comps, name =>
{
    comps.map(comp) =>
    {
        comparitor(comp.Item1, name, comp.Item2);
    }
    
}

```

8. Add a function to push a string onto the array only if the string is not empty

```
Action<ArrayList<T>,string> CheckPush = al, s =>
{
    s.map(s => s.Length > 0) 
    {
        al.Add(s);
    }
}

```
this part of the code might not work.  it uses a catamorphism to replace an if

9.  If 8 is broke, fix it.  :-)

10.  Add the CheckPush method

```
Func<ArrayList<string>,ArrayList<Tuple<Predicate<T>, string>>> ValidateName = comps, name =>
{
    ArrayList<string> al = new ArrayList<string>();

    comps.map(comp) =>
    {
        CheckPush(al,comparitor(comp.Item1, name, comp.Item2));
    }
    
}

```
11.  Finally inject the logging functionality into the validator

```

Func<ArrayList<string>,ArrayList<Tuple<Predicate<T>, string>>, Func<T>> ValidateName = comps, name, subclass =>
{
    ArrayList<string> al = new ArrayList<string>();

    comps.map(comp) =>
    {
        string s = comparitor(comp.Item1, name, comp.Item2);
        CheckPush(al,s);
        subclass.LogString(s);
    }
    
}


//invocation
var sl = MyStringLogger("start logging");
ArrayList<string> errors = ValidateName(stack, name, s1);

foreach(e in errors)
{
    console.write(e);
}
```