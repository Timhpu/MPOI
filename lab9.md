**Lab 9**

Preparation:
```r
install.packages('rvest')
library(rvest)
install.packages('stringr')
library(stringr)

url <- 'https://www.imdb.com/search/title/?count=100&release_date=2008,2019&title_type=feature'

html <- read_html(url)
m_rank <- html_text(html_elements(html, '.text-primary'))
m_title <- html_text(html_elements(html, '.lister-item-header a'))
m_runtime <- html_text(html_elements(html, '.text-muted .runtime'))

movies <- data.frame(m_rank, m_title, m_runtime, stringsAsFactors = FALSE)
names(movies) <- c('rank', 'title', 'runtime')
movies$rank <- strsplit(movies$rank, '.', fixed=TRUE)
movies$rank <- strtoi(movies$rank)
movies$runtime <- lapply(strsplit(movies$runtime, ' ', fixed=TRUE), function(l) l[[1]])
movies$runtime <- strtoi(movies$runtime)
```

1.
```
head(movies, 6)$title
```

2.
```
subset(movies, runtime>120)$title
```

3.
```
length(which(movies$runtime<100))
```
