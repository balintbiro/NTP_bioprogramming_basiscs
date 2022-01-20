4_prg_filehandling
================
Balint_Biro
1/19/2022

``` r
#writing text file (FASTA) line by line
#it is very important that you dont have to worry about new line characters
#since the elements of the vector (lines variable) will be recognized by R
#as lines so new line characters will be automatically introduced!
lines <- c('>header','AACTAGCTAGGGCTAGGCTTGGACTG')#variable with lines
myfile <- '../../results/myfasta.fa'#relative filepath
writeLines(lines, myfile)
print('File was created!')
```

    ## [1] "File was created!"

``` r
#reading text file line by line
myfile <- '../../results/myfasta.fa'#relative filepath
lines <- readLines(myfile)
lines
```

    ## [1] ">header"                    "AACTAGCTAGGGCTAGGCTTGGACTG"

``` r
#reading text file line by line with file.choose()
lines <- readLines(myfile)#very nifty function is file.choose() which
#will offer the available files
lines
```

    ## [1] ">header"                    "AACTAGCTAGGGCTAGGCTTGGACTG"

``` r
#write simple text file
lines <- c('>header\n','AACTAGCTAGGGCTAGGCTTGGACTG')#variable with lines
myfile <- '../../results/mytext.txt'#relative filepath
writeLines(lines, myfile)
#read text file
#install.packages('readtext')#package installation
#library(readtext)#import required modules
myfile <- '../../results/mytext.txt'#relative filepath
#lines <- readtext(myfile)#readtext module accepts only file with txt extension
lines
```

    ## [1] ">header\n"                  "AACTAGCTAGGGCTAGGCTTGGACTG"
