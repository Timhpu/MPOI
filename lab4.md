**Lab 4**

# apply() takes Data frame or matrix as an input and gives output in vector, list or array  
# lapply() function is useful for performing operations on list objects and returns a list object of same length of original set
# sapply() function takes list, vector or data frame as input and gives output in vector or matrix
# tapply() computes a measure or a function for each factor variable in a vector
  
1.
```r
list1 <-list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))
lapply(list1, FUN = sum) 

$observationA
[1] 40

$observationB
[1] 21
```

2.
```r
lapply(list1, FUN = range)
sapply(list1, FUN = range)

$observationA
[1] 1 7

$observationB
[1] 1 6

    observationA observationB
[1,]            1            1
[2,]            7            6
```

3.
```r
attach(InsectSprays)
tapply(InsectSprays$count, InsectSprays$spray, mean)
        A         B         C         D         E         F 
14.500000 15.333333  2.083333  4.916667  3.500000 16.666667 
```
