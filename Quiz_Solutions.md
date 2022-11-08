## Question 1 ##
# install.packages("nlme")
# install.packages("lattice") 
library(nlme)
library(lattice)

plot <- xyplot(weight ~ Time | Diet,BodyWeight)
class(plot)
# "trellis"

## Question 2 ##
library(nlme)
library(lattice)
xyplot(weight ~ Time | Diet, BodyWeight)
![q2q2](https://user-images.githubusercontent.com/82023279/200478424-1ce73aaf-3a43-4c6b-8ae6-fd94ada81646.png)


## Question 3 ##
panel.lmline()
panel.abline()

## Question 4 ##
library(lattice)
library(datasets)
data(airquality)
p <- xyplot(Ozone ~ Wind | factor(Month), data = airquality)

## Question 5 ##
trellis.par.set()

## Question 6 ##
the Grammar of Graphics developed by Leland Wilkinson

## Question 7 ##
library(datasets)
data(airquality)
airquality = transform(airquality, Month = factor(Month))
qplot(Wind, Ozone, data = airquality, facets = . ~ Month)
![q2q7](https://user-images.githubusercontent.com/82023279/200478583-57e98fb0-86b3-41f8-9e6f-2c960e2a5b93.png)


## Question 8 ##
a plotting object like point, line, or other shape

## Question 9 ##
library(ggplot2)
library(ggplot2movies)
g <- ggplot(movies, aes(votes, rating))
print(g)
ggplot does not yet know what type of layer to add to the plot.


## Question 10 ##
qplot(votes, rating, data = movies)
qplot(votes, rating, data = movies) + geom_smooth()
![q2q10](https://user-images.githubusercontent.com/82023279/200478616-5099bdf9-6157-4237-b691-90f98b82c422.png)
