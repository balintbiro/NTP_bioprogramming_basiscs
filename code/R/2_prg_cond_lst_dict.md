2_prg_cond_lst_dict
================
Balint_Biro
1/18/2022

``` r
#check whether the string contains the substring
string <- 'abcdefgh'
substring <- 'cde'
grep(substring, string)
```

    ## [1] 1

``` r
#logical variables 1
2==2
```

    ## [1] TRUE

``` r
#logical variables 1
2!=2
```

    ## [1] FALSE

``` r
#logical variables 2
2==3
```

    ## [1] FALSE

``` r
#simple conditional statement
if (2==2){
  print('Yes, 2 equals 2!')
}
```

    ## [1] "Yes, 2 equals 2!"

``` r
#more complicated conditional statment with "ELSE" branch
if (2==2){
  print('Yes, the first and second numbers are the same!')
}else{
  print('The two numbers are different!')
}
```

    ## [1] "Yes, the first and second numbers are the same!"

``` r
#more complicated conditional statment with "ELSE" branch
if (2==3){
  print('Yes, the first and second numbers are the same!')
}else{
  print('The two numbers are different!')
}
```

    ## [1] "The two numbers are different!"

``` r
#declaring list type variable version 1
mylist <- list(1,'a',TRUE)
mylist
```

    ## [[1]]
    ## [1] 1
    ## 
    ## [[2]]
    ## [1] "a"
    ## 
    ## [[3]]
    ## [1] TRUE

``` r
#declaring list type variable version 2
mylist <- vector("list",length=10)#empty list
mylist
```

    ## [[1]]
    ## NULL
    ## 
    ## [[2]]
    ## NULL
    ## 
    ## [[3]]
    ## NULL
    ## 
    ## [[4]]
    ## NULL
    ## 
    ## [[5]]
    ## NULL
    ## 
    ## [[6]]
    ## NULL
    ## 
    ## [[7]]
    ## NULL
    ## 
    ## [[8]]
    ## NULL
    ## 
    ## [[9]]
    ## NULL
    ## 
    ## [[10]]
    ## NULL

``` r
#check type of list variable
typeof(mylist)
```

    ## [1] "list"

``` r
#indexing a list type variable
mylist <- list(1,'a',TRUE)
mylist[[3]]
```

    ## [1] TRUE

``` r
#splitting up a string will result in a list
mystring <- 'abcdefg'
mylist <- strsplit(mystring,'')
mylist
```

    ## [[1]]
    ## [1] "a" "b" "c" "d" "e" "f" "g"
