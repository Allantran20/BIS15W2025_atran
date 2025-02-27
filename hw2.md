---
title: "Homework 2"
author: "Allan Tran"
date: "2025-01-09"
output:
  html_document: 
    theme: spacelab
    keep_md: yes
---

## Instructions
Answer the following questions and/or complete the exercises in RMarkdown. Please embed all of your code and push the final work to your repository. Your report should be organized, clean, and run free from errors. Remember, you must remove the `#` for any included code chunks to run.  

**1. Objects in R are a way in which we can store data or operations. Make a new object `pi` as 3.14159. You should now see the object `pi` in the environment window in the top right.** 

``` r
pi <- 3.14159
```

**2. Write a code chunk that divides `pi` by 2. Use the help command `?` to learn how to use the `round` function to limit your result to 3 significant digits.**  

``` r
pi/2
```

```
## [1] 1.570795
```

``` r
round(pi/2, 3)
```

```
## [1] 1.571
```

**3. Calculate the mean for the numbers 2, 8, 4, 6, 7, 4, 9, 9, 10. Please start by making a new object `x` that holds these values then use `mean` to perform the calculation.**  

``` r
x <- c(2, 8, 4, 6, 7, 4, 9, 9, 10)
mean(x)
```

```
## [1] 6.555556
```

**4. Make five new vectors that show the name, height in feet, and height in meters of the five tallest mountains in the world.**

``` r
name <- c("Mount Everest", "K2", "Kangchenjunga", "Lhotse", "Makalu")
height_feet <- c(29029, 28251, 28169, 27940, 27838)
height_meters <- c(8848, 8611, 8586, 8516, 8485)
```

**5. Combine these vectors into a data frame called `mountains`.**

``` r
mountains <- data.frame(name, height_feet, height_meters)
```

**6. What is the mean height of the mountains in feet?**

``` r
mean(mountains$height_feet)
```

```
## [1] 28245.4
```

**7. When were each of these mountains first climbed (i.e. in what year)? Make a new vector `first_climbed` and add it to the `mountains` data frame.**

``` r
first_climbed <- c(1953, 1954, 1955, 1956, 1955)
mountains <- data.frame(mountains, first_climbed)
mountains
```

```
##            name height_feet height_meters first_climbed
## 1 Mount Everest       29029          8848          1953
## 2            K2       28251          8611          1954
## 3 Kangchenjunga       28169          8586          1955
## 4        Lhotse       27940          8516          1956
## 5        Makalu       27838          8485          1955
```

**8. How many times have each of these mountains been climbed? Make a new vector `summits` and add it to the `mountains` data frame.**

``` r
summits <- c(1000, 300, 400, 400, 300)
mountains <- data.frame(mountains, summits)
mountains
```

```
##            name height_feet height_meters first_climbed summits
## 1 Mount Everest       29029          8848          1953    1000
## 2            K2       28251          8611          1954     300
## 3 Kangchenjunga       28169          8586          1955     400
## 4        Lhotse       27940          8516          1956     400
## 5        Makalu       27838          8485          1955     300
```

**9. Which mountain has the highest number of fatalities? Make a new vector `fatalities` and add it to the `mountains` data frame.**

``` r
fatalities <- c(300, 200, 100, 150, 100)
mountains <- data.frame(mountains, fatalities)
mountains
```

```
##            name height_feet height_meters first_climbed summits fatalities
## 1 Mount Everest       29029          8848          1953    1000        300
## 2            K2       28251          8611          1954     300        200
## 3 Kangchenjunga       28169          8586          1955     400        100
## 4        Lhotse       27940          8516          1956     400        150
## 5        Makalu       27838          8485          1955     300        100
```

**10. Write your data frame to a .csv file.**

``` r
write.csv(mountains, "mountains_data.csv", row.names = FALSE)
```

## Knit and Upload
Please knit your work as a .pdf or .html file and upload to Canvas. Homework is due before the start of the next lab. No late work is accepted. Make sure to use the formatting conventions of RMarkdown to make your report neat and clean!  
