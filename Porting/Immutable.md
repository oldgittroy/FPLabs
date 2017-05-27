** Convert stateful data into immutable data**

* Start with a stateful class

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
Modify class (type) to have only only getters, only the constructor sets data, and all variables are read only.

```
class MyStringLogger
{
    private string message;

    void MyStringLogger(string s)
    {
        message = s;
    }
}

```
---