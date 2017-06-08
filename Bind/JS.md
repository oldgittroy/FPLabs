**Using Bind in JavaScript**

1.  start with a class

```
function MyClass() {
    return {
        first: "",
        last: "",
        add: function() {
            return this.first + this.last;
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
var fullName = MyClass().add.bind(name);

```
