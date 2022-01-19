3_prg_loops
================
Balint_Biro
1/19/2022

``` r
#declare a variable
mylist <- list(12,'YES',TRUE,'12',c(1,2,3))
mylist
```

    ## [[1]]
    ## [1] 12
    ## 
    ## [[2]]
    ## [1] "YES"
    ## 
    ## [[3]]
    ## [1] TRUE
    ## 
    ## [[4]]
    ## [1] "12"
    ## 
    ## [[5]]
    ## [1] 1 2 3

``` r
#iterate over the items of a previously declared variable with a for loop
for (element in mylist){
  print(element)
}
```

    ## [1] 12
    ## [1] "YES"
    ## [1] TRUE
    ## [1] "12"
    ## [1] 1 2 3

``` r
#add up elements in a list
mylist <- list(1,2,3,4,5,6)
sum_of_mylist <- 0
for (number in mylist){
  sum_of_mylist <- sum_of_mylist+number
}
sum_of_mylist
```

    ## [1] 21

``` r
#while loop, in the head of the loop you have to declare a condition. While the
#condition is TRUE, the loop will iterate. AKA forward testing loop since the
#program will check the condition in the head of theloop and if it is FALSE it
#wont execute the body of the loop
tracker <- 0
while (tracker<10){
  print(tracker)
  tracker <- tracker+1
}
```

    ## [1] 0
    ## [1] 1
    ## [1] 2
    ## [1] 3
    ## [1] 4
    ## [1] 5
    ## [1] 6
    ## [1] 7
    ## [1] 8
    ## [1] 9

``` r
#repeat loop. The very important difference between repeat and while, that the
#program will execute the body of the repeat loop once even if the condition is
#false since its at the end of the body. But in case of while loop if the
#condition in the head of the loop is FALSE, the program wont enter the body of
#the loop
tracker <- 0
repeat{
  print(tracker)
  tracker <- tracker+1
  if (tracker>10){
    break
  }
}
```

    ## [1] 0
    ## [1] 1
    ## [1] 2
    ## [1] 3
    ## [1] 4
    ## [1] 5
    ## [1] 6
    ## [1] 7
    ## [1] 8
    ## [1] 9
    ## [1] 10

``` r
#repeat loop. The very important difference between repeat and while, that the
#program will execute the body of the repeat loop once even if the condition is
#false since its at the end of the body. But in case of while loop if the
#condition in the head of the loop is FALSE, the program wont enter the body of
#the loop
tracker <- 0
repeat{#it executed the body once!
  print(tracker)
  tracker <- tracker+1
  if (tracker>0){
    break
  }
}
```

    ## [1] 0

``` r
#controlling mechanism <- next
mylist <- list(1,2,3,'a',4,5,6,'b',7,8)
letters <- list('a','b')
for (i in mylist){
  if (i %in% letters){
    print('Character, so cannot use in math and Im gonna jump it over!')
    next
  }
  print(as.numeric(i)+2)
}
```

    ## [1] 3
    ## [1] 4
    ## [1] 5
    ## [1] "Character, so cannot use in math and Im gonna jump it over!"
    ## [1] 6
    ## [1] 7
    ## [1] 8
    ## [1] "Character, so cannot use in math and Im gonna jump it over!"
    ## [1] 9
    ## [1] 10
