---
title: "Week2 Assignment"
author: "Rohit Jain"
date: "August 13, 2018"
output: html_document
---

### Loading data and preprocessing


```r
dt <- read.csv("activity.csv")
dtWithoutNA <- na.omit(dt)
sumStep <- by(dtWithoutNA$steps, dtWithoutNA$date, sum,simplify = TRUE)
sumStep[is.na(sumStep)] <- 0
```

### Part 1:  Mean total number of steps taken per day

This part will answer the question for the part 1 of the assignment:


#### 1. Calculate the total number of steps taken per day.



```r
print(sumStep)
```

```
## dtWithoutNA$date: 2012-10-01
## [1] 0
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-02
## [1] 126
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-03
## [1] 11352
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-04
## [1] 12116
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-05
## [1] 13294
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-06
## [1] 15420
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-07
## [1] 11015
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-08
## [1] 0
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-09
## [1] 12811
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-10
## [1] 9900
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-11
## [1] 10304
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-12
## [1] 17382
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-13
## [1] 12426
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-14
## [1] 15098
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-15
## [1] 10139
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-16
## [1] 15084
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-17
## [1] 13452
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-18
## [1] 10056
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-19
## [1] 11829
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-20
## [1] 10395
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-21
## [1] 8821
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-22
## [1] 13460
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-23
## [1] 8918
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-24
## [1] 8355
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-25
## [1] 2492
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-26
## [1] 6778
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-27
## [1] 10119
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-28
## [1] 11458
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-29
## [1] 5018
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-30
## [1] 9819
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-10-31
## [1] 15414
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-01
## [1] 0
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-02
## [1] 10600
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-03
## [1] 10571
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-04
## [1] 0
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-05
## [1] 10439
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-06
## [1] 8334
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-07
## [1] 12883
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-08
## [1] 3219
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-09
## [1] 0
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-10
## [1] 0
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-11
## [1] 12608
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-12
## [1] 10765
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-13
## [1] 7336
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-14
## [1] 0
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-15
## [1] 41
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-16
## [1] 5441
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-17
## [1] 14339
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-18
## [1] 15110
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-19
## [1] 8841
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-20
## [1] 4472
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-21
## [1] 12787
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-22
## [1] 20427
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-23
## [1] 21194
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-24
## [1] 14478
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-25
## [1] 11834
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-26
## [1] 11162
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-27
## [1] 13646
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-28
## [1] 10183
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-29
## [1] 7047
## -------------------------------------------------------- 
## dtWithoutNA$date: 2012-11-30
## [1] 0
```

#### 2. Make a histogram of the total number of steps taken each day.



```r
barplot(sumStep,
        las=2,
        col= "red",
        main = "Total Number of Steps taken per day",
        xlab = "Date",
        ylab = "Total Steps",
        cex.names = 0.5,
        cex.axis = 1
        )
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3-1.png)

#### 3. Calculate and report the mean and median of the total number of steps taken per day.


```r
paste("mean:" , mean(sumStep,na.rm = TRUE))
```

```
## [1] "mean: 9354.22950819672"
```

```r
paste("median:", median(sumStep,na.rm = TRUE))
```

```
## [1] "median: 10395"
```

### Part 2:  Average daily activity pattern

This part will answer the question for the part 2 of the assignment:

#### Data Preprocessing


```r
dtWithoutNA$interval <- as.factor(dtWithoutNA$interval)
avgSteponInterval <- by(dtWithoutNA$steps, dtWithoutNA$interval, mean,simplify = TRUE)
```

#### 1.  time series plot of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis):


```r
plot(levels(dtWithoutNA$interval),avgSteponInterval,
     type = "l",
     col = "red",
     main = "Average Steps as per the interval",
     xlab = "Levels",
     ylab = "Average Steps"
     )
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6-1.png)

#### 2. 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps:


```r
interval <- levels(as.factor(dtWithoutNA$interval))
avgStep <- as.vector(avgSteponInterval)
avgStep <- as.data.frame(avgStep,stringAsFactor = FALSE)
avgStep <- cbind(avgStep,interval)
temp <- avgStep[avgStep$avgStep == max(avgStep$avgStep),]
paste("Interval with maximum number of steps", temp$interval)
```

```
## [1] "Interval with maximum number of steps 835"
```

### Part 3:  Imputing missing values

This part will answer the question for the part 2 of the assignment:

#### 1. Total number of NA in the dataset

```r
sum(is.na(dt$steps))
```

```
## [1] 2304
```


#### 2 & 3. Strategy for filling in all of the missing values in the dataset and created the dataset "dt" with missing value imputed with 0


```r
dt[is.na(dt)] <- 0
sumStepwithImputing <- by(dt$steps, dt$date, sum,simplify = TRUE)
sumStepwithImputing[is.na(sumStepwithImputing)] <- 0
```

#### 4.Histogram of the total number of steps taken each day and mean and median total number of steps taken per day.


```r
barplot(sumStepwithImputing,
        las=2,
        col= "green",
        main = "Total Number of Steps taken per day",
        xlab = "Date",
        ylab = "Total Steps",
        cex.names = 0.5,
        cex.axis = 1
        )
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-10-1.png)

There is no diffrence in the mean and mode of the dataset when imputing 0 for the NAs in the dataset, as 0 doesn't have any impact on the mean or meadian of the data set.


```r
library(knitr)
kable(c(paste("mean with imputing:" , mean(sumStepwithImputing)),
        paste("mean without imputing:" , mean(sumStep,na.rm = TRUE)),
        paste("median with imputing:", median(sumStepwithImputing)),
        paste("median without imputing:", median(sumStep,na.rm = TRUE))
        ), caption = "Mean and Median compairision")
```



|x                                       |
|:---------------------------------------|
|mean with imputing: 9354.22950819672    |
|mean without imputing: 9354.22950819672 |
|median with imputing: 10395             |
|median without imputing: 10395          |

### Part 4:  Activity patterns between weekdays and weekends

#### 1. Factor variable in the dataset with two levels - "weekday" and "weekend"


```r
dt <- read.csv("activity.csv")
dt[is.na(dt)] <- 0
dt$date <- as.Date(dt$date, format = "%Y-%m-%d")
dt$day <- weekdays(dt$date)
temp1 <- dt$day %in% c("Thursday","Monday","Tuesday","Wednesday","Friday")
temp2 <- dt$day %in% c("Saturday","Sunday")
dt$day[temp1] <- "weekday"
dt$day[temp2] <- "weekend"
dt$day <- as.factor(dt$day)
```

#### 2. Panel plot containing a time series plot


```r
library(ggplot2)
averages <- aggregate(steps ~ interval + day, data=dt, mean)
ggplot(averages, aes(interval, steps)) + geom_line() + facet_grid(day ~ .) + xlab("5-minute interval") + ylab("Number of steps")
```

![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-13-1.png)
