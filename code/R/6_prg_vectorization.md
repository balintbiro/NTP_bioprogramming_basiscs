6_prg_vectorization
================
Balint Biro
2/8/2022

Vectorization and vector operations are very important ideas in R. R
language is somehow similar to Python in a sense that it has functions
written in low level languages. That fact makes vectorized code runs
faster than devectorized code.

``` r
#create a vector in a vectorized way by repeating "R programming" x times
system.time(
  myvector <- rep("R programming",10000000)
)
```

    ##    user  system elapsed 
    ##   0.069   0.013   0.082

``` r
#create a vector in a devectorized way
myvector <- 1:10000000
system.time(
  for(i in myvector){
    myvector[i] <- "R programming"
  }
)
```

    ##    user  system elapsed 
    ##   4.572   0.321   4.907

``` r
#the most widely used way to generate a vector 
myvector <- 1:10
is.vector(myvector)
```

    ## [1] TRUE

``` r
myvector
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10

``` r
#if we have datapoints and we wanna create a vector from them
myvector <- c(1,12,43,2)
is.vector(myvector)
```

    ## [1] TRUE

``` r
myvector
```

    ## [1]  1 12 43  2

``` r
#the conventional indexing can be applied
myvector[2]
```

    ## [1] 12

``` r
#it is important that in R we can name the elements inside the vector
myvector
```

    ## [1]  1 12 43  2

``` r
names(myvector) <- c("first","second","third","fourth")
myvector
```

    ##  first second  third fourth 
    ##      1     12     43      2

``` r
#of course a very important feature of vectors in R that they behave like the
#vectors in mathematics so the vector operations can be applied
v1 <- 1:5
v2 <- 6:10
v1
```

    ## [1] 1 2 3 4 5

``` r
v2
```

    ## [1]  6  7  8  9 10

``` r
v1+v2
```

    ## [1]  7  9 11 13 15
