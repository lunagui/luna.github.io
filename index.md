---
title       : My First Forecast in Real World
subtitle    : Data Science Research
author      : Luna
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Why Forecast

1. Forecasting is required in many situations  
   From Stock market to House price, there are lost of demending out there.  
2. More practical for one person  
   I really want to creat a Robot, but it's hard to do it by myself.  
     
3. It's fun!  

--- 

## My first try
![alt text][111]

[111]: figure/screenshot.png "Title"

The APP live here: [https://luna.shinyapps.io/rents/](https://luna.shinyapps.io/rents/)

---
1. The data  
  I download the [data](http://www.dbh.govt.nz/nz-housing-and-construction-quarterly-open-data) comes from MBIE’s tenancy bond database, which records all new rental bonds that are lodged each month.  
  
2. Forecast for Auckland  


```r
DT <- read.csv("data/geometric-mean-rents-by-ta.csv")
ts1 <- ts(subset(DT, select = Auckland), start = 1993, frequency=12)
ets1 <- ets(ts1,model="MMM");forec <- forecast(ets1, h = 12);plot(forec)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

---
## Futher

1. That will be better if we can add more factors like bedrooms, bathrooms or Land area. They had raw data, but that based on how well I can understand them.

2. Forecast is a special fild of data since, which need more understanding of method R used to. I will dig them more.

3. Welcome anybody that intersted in and cantact with me: guiliying@gmail.com

  






