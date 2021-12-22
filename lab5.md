**Lab 5**

```r
install.packages('readxl')
library(readxl)

url = 'https://data.gov.ua/dataset/017ce04c-5a83-4832-b116-2b9bafca5cfa/resource/7e965fe4-8abe-477c-b3df-a05bbe2c96d7/download/list.xlsx'
filename = 'list.xlsx'

download.file(url, filename, mode='wb')
data <- read_excel(filename, 1)
```
New names:
* `` -> ...1
* `` -> ...2
* `` -> ...3
* `` -> ...4
* `` -> ...5
* ...
```
head(data, n=6)
```
 A tibble: 6 x 15
...1   ...2  ...3   ...4  ...5  ...6  ...7  ...8  ...9  `<U+0414><U+043E><U+0434><U+0430><U+0442><U+043E><U+043A> 2\n<U+0434><U+043E> ~ ...11
 <chr>  <chr> <chr>  <chr> <chr> <chr> <chr> <chr> <chr> <chr>            <chr>
1 <NA>   <NA>  <NA>   <NA>  <NA>  <NA>  <NA>  <NA>  <NA>  <NA>             <NA> 
2 <NA>   <NA>  <NA>   <NA>  <NA>  <NA>  <NA>  <NA>  <NA>  <NA>             <NA> 
3 <NA>   <NA>  <U+0414><U+0430><U+0442><U+0430> ~ <NA>  <NA>  <NA>  <NA>  <NA>  <NA>  <NA>             <NA> 
4 <U+0423><U+0441><U+0442><U+0430><U+043D>~ <NA>  <U+0423><U+043F><U+0440><U+0430><U+0432>~ <NA>  <NA>  <NA>  <NA>  <NA>  <NA>  <U+0437><U+0430> <U+0404><U+0414><U+0420><U+041F><U+041E><U+0423>        <NA> 
5 <U+0422><U+0435><U+0440><U+0438><U+0442>~ <NA>  <U+0413><U+0430><U+0439><U+0432><U+043E>~ <NA>  <NA>  <NA>  <NA>  <NA>  <NA>  <U+0437><U+0430> <U+041A><U+041E><U+0410><U+0422><U+0423><U+0423>        <NA> 
6 <U+041E><U+0440><U+0433><U+0430><U+043D>~ <NA>  <U+041E><U+0440><U+0433><U+0430><U+043D>~ <NA>  <NA>  <NA>  <NA>  <NA>  <NA>  <U+0437><U+0430> <U+041A><U+041E><U+041F><U+0424><U+0413>         <NA> 
 ... with 4 more variables: ...12 <chr>, ...13 <chr>, ...14 <chr>, ...15 <chr>
```
