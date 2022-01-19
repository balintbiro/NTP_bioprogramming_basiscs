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
#add new element to a list
mylist <- list(1,'a',123.2,TRUE,c(12,3,4))
mylist
```

    ## [[1]]
    ## [1] 1
    ## 
    ## [[2]]
    ## [1] "a"
    ## 
    ## [[3]]
    ## [1] 123.2
    ## 
    ## [[4]]
    ## [1] TRUE
    ## 
    ## [[5]]
    ## [1] 12  3  4

``` r
#add new element to a list
mylist <- append(mylist,'new_element')
mylist
```

    ## [[1]]
    ## [1] 1
    ## 
    ## [[2]]
    ## [1] "a"
    ## 
    ## [[3]]
    ## [1] 123.2
    ## 
    ## [[4]]
    ## [1] TRUE
    ## 
    ## [[5]]
    ## [1] 12  3  4
    ## 
    ## [[6]]
    ## [1] "new_element"

``` r
#splitting up a string will result in a list
mystring <- 'abcdefg'
mylist <- strsplit(mystring,'')
mylist
```

    ## [[1]]
    ## [1] "a" "b" "c" "d" "e" "f" "g"

``` r
#create dictionary type variable <- dictionary consists of key/value pairs
genes <- c('cntnap'='chr2:100-2000','ptprc'='chr4:2300-2900','lrrc4c'='chr7:10-1900')
genes
```

    ##           cntnap            ptprc           lrrc4c 
    ##  "chr2:100-2000" "chr4:2300-2900"   "chr7:10-1900"

``` r
#accessing one element (key/value pair) of a dictionary
genes['cntnap']
```

    ##          cntnap 
    ## "chr2:100-2000"

``` r
#accessing just the value of a given key with type conversion
as.character(genes['cntnap'])
```

    ## [1] "chr2:100-2000"

``` r
#add new element (aka item, key/value pair) to the dictionary
genes['sept10'] <- 'chr9:278-3970'
genes
```

    ##           cntnap            ptprc           lrrc4c           sept10 
    ##  "chr2:100-2000" "chr4:2300-2900"   "chr7:10-1900"  "chr9:278-3970"
