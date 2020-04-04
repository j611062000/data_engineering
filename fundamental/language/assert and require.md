`assert` wiil trigger `AssertionError` once the assertion failed, and `require`
will cause `IlleagalArgumentException`. Though from the aspect of functionality, both of them looks alomost the same, however, the semantic is different.

1. `assert` should be considered as "to check the code of the function itself"
2. `require` implies "to enforce a precondition on the caller of a function"

ref: https://stackoverflow.com/questions/26140757/what-to-choose-between-require-and-assert-in-scala