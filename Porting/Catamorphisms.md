**Using Catamorphisms in C#**


1.  Set up a star object

```
Tuple<double, double, double> star = new Tuple<double, double>(1.0,1.0,2.5); 

```
2.  Make an array list of stars

```
ArrayList<Tuple<double, double, double>> LocalGroup = new ArrayList<Tuple<double, double, double>>();

```

3.  populate the group of stars

```
for (var i=0; i<10; i++)
{
    double randomx = 
    double randomy =
    double vel = 
    LocalGroup.Add(new Tuple<double, double>(randomx, randomy, vel));
}

```

4.  The old way of making arrays seems to fail with tuples

```
Tuple<double, double, double>[10] LocalGroup;

```

5.  Make a list of a fixed size

```
List<int> particles = new int[10] {1,2,3,4,5,6,7,8,9,10};

```
its a bit like the sequence in F#

```
let particles = [1..10]

```
6.  Now replace the for loop with a catamorphism

```
var InitParticles = particles.map(x=>
    {
        double randomx = 
        double randomy =
        vel = 
        LocalGroup.Add(new Tuple<double, double>(randomx, randomy, vel));

        return x;
    }
);

```
we now have the stars in our local group set up

7.  Plug the LocalGroup into a drawing function

```
var Draw = LocalGroup.map(x=> render(x.Item1, x.Item2));

```

render can come from any random graphics library.  Maybe canvas in JavaScript.

8.  Add some movement

```
LocalGroup = LocalGroup.map(x=>{
    return new Tuple<double, double, double>(x.Item1, x.Item2, x.Item1 + x.Item3);
});

//watch your stars go streaking off into the sky
Draw();

```



