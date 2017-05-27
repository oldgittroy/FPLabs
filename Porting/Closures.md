**Convert Classes and Methods to Closures and Functions**


1. Start with our old friend, the logger class.

```

class MyStringLogger
{
    bool Flag;
    int counter;
    string message;

    bool testFlag()
    {
        return Flag;
    }

    void LogString(string s)
    {
        string = s;
        counter++;
    }

    int getCount()
    {
        return counter;
    }

}
```


2. Make a Func to replace the class

```
Func<> MyStringLogger = ()=>
{

}

```


3.  Adding the class member variables into the Func will allow closures to access them as free variables

```
Func<> MyStringLogger = ()=>
{
    bool Flag;
    int counter;
    string message;
}

```

4.  Consolidate the inputs and outputs

* Inputs:  string
* Outputs:  bool, int


Start with the input.  We will do the output later. 

```
Func<void, string> MyStringLogger = (s)=>
{
    string message = s;
}

```

5.  Add in the methods

```
Func<void, string> MyStringLogger = (s)=>
{
    bool Flag;
    int counter;
    string message = s;

    Func<bool> testFlag => 
    {
        return Flag;
    }

    Func<void, string> LogString = (s1)=>
    {
        message = s1;
        counter++;
    }

    Func<int, void> getCount =>
    {
        return counter;
    }

}

```

6.  Clean up the get methods


```
Func<void, string> MyStringLogger = (s)=>
{
    bool Flag;
    int counter;
    string message = s;

    Func<bool, void> testFlag => Flag;

    Action<string> LogString = (s1)=>
    {
        message = s1;
        counter++;
    }

    Func<int, void> getCount => counter;

}

```

7.  Replace the variables with a tuple


```
Func<void, string> MyStringLogger = (s)=>
{
    Tuple<int, string, bool> data = new Tuple<int, string, bool>(0, s, false);

    Func<bool, void> testFlag => data.Item3;

    Action<string> LogString = (s1)=>
    {
        data.Item2 = s1;
        data.Item1++;
    }

    Func<int, void> getCount => data.Item1;

}

```

8.  Finally, replace the getter methods with the tuple


```
Func<Tuple<int, string, bool>, string> MyStringLogger = (s)=>
{
    Tuple<int, string, bool> data = new Tuple<int, string, bool>(0, s, false);

    Action<string> LogString = (s1)=>
    {
        data.Item2 = s1;
        data.Item1++;
    }

    return data;
}

```

9.  Invoke the closure

```
var sl = MyStringLogger("First item");
s1.LogString("something else to log");

console.write("logger: {0},{1},{2}", s1.Item1, s1.Item2, s1.Item3);

```
10.  Your turn...

Pull the string value out of the tuple so its private


11. Replace the string with an array, list, or other dynamic data structure


