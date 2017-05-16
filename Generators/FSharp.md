**Generators in F#**

implemented via the sequence type

1.  write a simple sequence

```
seq { for i in 1 .. 10 do yield i * i }

```
2.  write the sequence in functional shorthand

```
seq { for i in 1 .. 10 -> i * i }

```
