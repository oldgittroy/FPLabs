**Bind in F#**


1.  Create a bind operator

```
let (>>=) x y = pipeInto(x,y)

```
2.  use  bind 

```
let bar = "bar"
let strFoo = Some("foo")
let printfoo s = 
    s + "foo"

bar.bind printfoo strFoo

```
3.  use the bind operator

```
bar >>== printfoo strFoo

```
