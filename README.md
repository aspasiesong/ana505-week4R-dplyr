# ANA505: Week 4 R - dplyr
a repository to hold my week 4 R activity code - Topic: dplyr package
```ruby
#ANA-505 Data Mining
#Week 4: dplyr package
#Aspasie Song
#Student ID: 1111682

rm(list=ls()) #removes all variables stored previously 

#Task: Write the code to get a dataset from Base R: ChickWeight
#and save it as a dataframe with a new name that includes your first name
data("ChickWeight")
AspasieChickWeight <- data.frame(ChickWeight)

#See the top rows of the data
#TASK: Write the code to see the top rows of the data
library(package = "dplyr")
slice(.data = AspasieChickWeight, c(1:1))

#Install and call the package dplyr
#TASK: Write the code to install and call dplyr
install.packages("dplyr")
library(package = "dplyr")

#Let's just see the weight and Time columns
#Task: Write the code to 'select' just the weight and Time columns 
#(hint: use the 'select' function)
AspasieChickWeight %>% select(weight, Time)

#Let's name the dataset with just the two columns, weight and Time
#TASK: Write the code to save the two columns as a new dataframe
#and give it a new name
weightTime <- AspasieChickWeight %>% select(weight, Time)

#Let's get rid of the Time column in the new dataframe created above
#TASK: Write the code that deselects the Time column
#(hint: use the 'select' function to not select a -column)
weightTime %>% select(weight)

#Let's rename a column name
#TASK: Write the code that renames 'weight' to 'ounces'
AspasieChickWeight %>% rename(ounces = weight)

#Let's make a new dataframe with the new column name
#TASK: Write the code that names a new dataframe that includes the 'ounces' column
AspasieChickOz <- AspasieChickWeight %>% rename(ounces = weight)

#Let's 'filter' our dataframe to only those with a 1 in the Chick column
#TASK: Write the code that includes only rows where Chick = 1
AspasieChickOz %>% filter(Chick == "1")

#Let's 'group' our data by Diet
#TASK: Write the code to group the data by Diet (hint: group_by)
group_by(AspasieChickOz, Diet)
df1 <- group_by(AspasieChickOz, Diet)

#Task: add one of the other codes (not in the tasks above) 
#you learned about from the dplyr package
summarise(df1, avgOz = mean(ounces))  #calculates the average weight(oz) of each diet group
```
