# Call by value and name

```scala
    def callByValue(x: Int) = {
        println("x1=" + x)
        println("x2=" + x)
    }

    def callByName(x: => Int) = {
        println("x1=" + x)
        println("x2=" + x)
    }

    def y = {
        print("hi\n")
        2
    }
```
Then we call the functions:
```scala
    callByValue(y)
    callByName(y)
```
The result is:
```scala
//callByValue
hi
x1=1
x2=1

//callByName
hi
x1=1
hi
x2=1
```

Explanation:
Because the if the function is invoked by `call by name`, the passed-in argument(s) will be evaluated every time it is referenced.

Futhermore, let's look at the example below.

```scala
def x = 2
val y = 2
```
Whichever you refer, the result will be the same, howerver, the underlying are quite different. The `def x = 2` could be considered as a function which always return `2`. In other words, it is evaluated whenever you call it. Sounds famimiliar? It's actually `call by name`. The latter one is `call by value`. Since Scala will cache the result of `val y = 2`. It will not be evaluated again.

Ref
1. https://stackoverflow.com/questions/13337338/call-by-name-vs-call-by-value-in-scala-clarification-needed