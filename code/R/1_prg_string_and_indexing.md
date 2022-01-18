1_prg_string_and_indexing
================
Balint_Biro
1/18/2022

``` r
#variable declaration, quotation marks mean that the inner stuff is gonna be a string
message <- 'hello world!'
message
```

    ## [1] "hello world!"

``` r
#the return value of the typeof() function is gonna be the actual data type of a variable
typeof(message)
```

    ## [1] "character"

``` r
#check the length of our character (string) variable
nchar(message)
```

    ## [1] 12

``` r
#purely typed number have a datatype "double" which refers to the double precision floating point number
number <- 123
typeof(number)
```

    ## [1] "double"

``` r
#declaring integer type variables
number <- 3L
typeof(number)
```

    ## [1] "integer"

``` r
#indexing in R is 1 based
string <- 'This is a sample string!'
substring(string,1,3)
```

    ## [1] "Thi"
