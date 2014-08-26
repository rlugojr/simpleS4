# simpleS4

[![Build Status](https://travis-ci.org/hadley/simpleS4.png?branch=master)](https://travis-ci.org/hadley/simpleS4)

This package illustrates the correct way to depend on the methods package, in order to use S4.  You need to do two things:

* In DESCRIPTION, `Depends: methods`
* In NAMESPACE, "imports(methods)"

This passes R CMD check, and works when run from Rscript:

    Rscript --vanilla -e "library(simpleS4); test()"
    Rscript --vanilla -e "simpleS4::test()"

`test()` is defined as:

```r
test <- function() {
  A <- new("A")
  print(A)
}
```
