**Lab 7**

```r
install.packages('XML')
install.packages('methods')

library('XML')
library('methods')

url <- 'http://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Frestaurants.xml'
data <- xmlParse(url, useInternalNodes=TRUE)
data <- xmlToDataFrame(xpathApply(data, '/response/row/row'))

length(which(data$zipcode == '21231'))
```
