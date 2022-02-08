5_prg_functions
================
Balint Biro
2/8/2022

``` r
#simplest function returns with the input
myfunction <- function(x){
  return(x)
}
myfunction("x")
```

    ## [1] "x"

``` r
#next level complicated function which uses the input to create the return value
#aka output
greetings <- function(name){#head of the function
  message <- paste("how you doin'",name,"?")
  return(message)
}
greetings("Pista")
```

    ## [1] "how you doin' Pista ?"
