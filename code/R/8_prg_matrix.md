8_prg_matrix
================

When it comes to table representation in programming, two things need to
be considered, matrices and data frames. As we have discussed it in
terms of Python, key feature that differentiates matrices from data
frames is that matrices can only contain one type of data while data
frames can contain mixed datatypes.

``` r
#matrix construction I
#with the cbind() function, you can basically provide the vectors as columns
mymatrix <- cbind(c(1,2,3),c(9,8,7))
mymatrix
```

    ##      [,1] [,2]
    ## [1,]    1    9
    ## [2,]    2    8
    ## [3,]    3    7

``` r
#matrix construction I
#with the rbind() function, you can basically provide the vectors as rows
mymatrix <- rbind(c(1,2,3),c(9,8,7))
mymatrix
```

    ##      [,1] [,2] [,3]
    ## [1,]    1    2    3
    ## [2,]    9    8    7

``` r
#it is possible to name the dimensions of the matrix
colnames(mymatrix) <- c("column 1st","column 2nd","column 3rd")
rownames(mymatrix) <- c("row 1st","row 2nd")
mymatrix
```

    ##         column 1st column 2nd column 3rd
    ## row 1st          1          2          3
    ## row 2nd          9          8          7

``` r
#data frame (df) construction is kinda same
df <- data.frame(column_1st=c(1,2,"three"),column_2nd=c(9,8,"seven"))
rownames(df) <- c("row 1st","row 2nd","row 3rd")
df
```

    ##         column_1st column_2nd
    ## row 1st          1          9
    ## row 2nd          2          8
    ## row 3rd      three      seven
