**Lab 6**

```r
url = 'https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Fss06hid.csv'
filename = 'lab6_data.xlsx'

setwd('E:\\university\\master\\year2\\sem1\\r\\labs')
download.file(url, filename, mode='wb')
data <- read.csv(filename)

# Remove all NAs and non-numbers
data <- Filter(is.numeric, data)
data[is.na(data)] <- 0

apply(data, 2, function(x){sum(x>1000000)})
sum(apply(data, 2, function(x){sum(x>1000000)}) > 0)
```
