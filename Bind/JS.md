**Using Bind in JavaScript**

1.  start with a class

```
function MyClass() {
    return {
        add: function(x, y) {
            return x + y;
        },
        subtract: function(x,y){
            return x -y;
        }
    }
}

```
2.  Now create an object

```
var name = {
    first: "john",
    last: "doe"
}

```
3.  bind the data to the function

```
var fullName = MyClass.add.bind(name);

```
