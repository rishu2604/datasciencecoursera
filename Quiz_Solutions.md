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
