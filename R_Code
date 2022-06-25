#install and read the package we want
install.packages("data.table")
install.packages("haven")
library("data.table")
library("haven")

# read the data document and add the column of year
document_name <- data.table(document_name, YEAR = rep(specific_year))

#extract the county level data
document_name <- subset(document_name, LEVEL == 1)

#extract the variable you want
document_name <- document_name[, c("variable 1","variable 2")] 

#rename the column
names(document_name)[names(document_name) == "old name"] <- "new name"

#delete the NA data
document_name <- na.omit(document_name)

#check the data to see if it fits (just like what Mathias do in the course)
summay(document_name)
