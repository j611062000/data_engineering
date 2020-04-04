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
```
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

Ref
1. https://stackoverflow.com/questions/13337338/call-by-name-vs-call-by-value-in-scala-clarification-needed