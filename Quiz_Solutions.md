## Question 1 ##
colClasses=c("character", "character", rep("numeric",7))
df <- read.csv("household_power_consumption.txt"
               , sep = ";"
               , colClasses = colClasses
               , na.strings = '?'
               , )

df[, 'Date'] <- dmy(df[, 'Date'])
df[, 'Time'] <- hms(df[, 'Time'])
df <- subset(df, Date >= "2007-02-01" & Date <= "2007-02-02")

![image](https://user-images.githubusercontent.com/82023279/200479039-c8a3904d-d2c1-4c28-8532-328a00486ccb.png)


## Question 2 ##
colClasses=c("character", "character", rep("numeric",7))
df <- read.csv("household_power_consumption.txt"
               , sep = ";"
               , colClasses = colClasses
               , na.strings = '?'
               , )

df[, 'Date'] <- dmy(df[, 'Date'])
df[, 'Time'] <- hms(df[, 'Time'])
df <- subset(df, Date >= "2007-02-01" & Date <= "2007-02-02")

![image](https://user-images.githubusercontent.com/82023279/200479185-f51775b4-4496-411d-92de-389d516e6f1b.png)


## Question 3 ##
colClasses=c("character", "character", rep("numeric",7))
df <- read.csv("household_power_consumption.txt"
               , sep = ";"
               , colClasses = colClasses
               , na.strings = '?'
               , )

df[, 'Date'] <- dmy(df[, 'Date'])
df[, 'Time'] <- hms(df[, 'Time'])
df <- subset(df, Date >= "2007-02-01" & Date <= "2007-02-02")

df[,'Datetime'] <- df$Date + df$Time
![image](https://user-images.githubusercontent.com/82023279/200479799-f2339256-02df-4703-ad9a-f43cf2c8c2b9.png)


## Question 4 ##
colClasses=c("character", "character", rep("numeric",7))
df <- read.csv("household_power_consumption.txt"
               , sep = ";"
               , colClasses = colClasses
               , na.strings = '?'
               , )

df[, 'Date'] <- dmy(df[, 'Date'])
df[, 'Time'] <- hms(df[, 'Time'])
df <- subset(df, Date >= "2007-02-01" & Date <= "2007-02-02")

# Plot 4

df[,'Datetime'] <- df$Date + df$Time

png("plot4.png", width=480, height=480)

par(mfrow=c(2,2))

with(df, plot(Datetime, Global_active_power
              , type='l'
              , xlab=""
              , ylab="Global Active Power"))

with(df, plot(Datetime, Voltage
              , type='l'
              , xlab="datetime"
              , ylab="Voltage"))

with(df, {
  plot(Datetime, Sub_metering_1
       , col="black"
       , type='l'
       , ylab="Energy sub metering"
       , xlab="")
  
  lines(Datetime, Sub_metering_2, col="red")
  lines(Datetime, Sub_metering_3, col="blue")
  legend("topright"
         , legend=c("Sub_metering_1", "Sub_metering_2", "Sub_metering_2")
         , col=c("black", "red", "blue")
         , lty= 1
         , bty = "n")
})


with(df, plot(Datetime, Global_reactive_power
              , type='l'
              , xlab="datetime"
              , ylab="Global_reactive_power"))


dev.off()
![image](https://user-images.githubusercontent.com/82023279/200479904-060efc6a-f9c8-4111-bbfd-f815118a2794.png)
