# R-markdown-code-assignment-2

---
title: "ANA 515 Assignment 2"
author: "Abdul Moid"
date: "2023-06-14"
output: html_document
theme:
 bootswatch: "cosmo"
---
```{r code1, echo=TRUE}

#Section 1: Description of the data

# The dataset being used is a file called "bad-drivers.csv" from the FiveThirtyEight GitHub 
repository. This dataset measures various factors related to bad driving behavior in the United 
States. It includes information on the number of accidents, speeding tickets, DUIs, and other 
related variables for each state. The data was collected through a survey and contains statistics 
from different states in the US. The dataset is saved in a CSV (Comma-Separated Values) format, 
which is a common file format for storing tabular data. In a CSV file, each row represents a 
record, and the values within each row are separated by commas. The delimiter used in this 
dataset is a comma. To read and analyze this dataset, we will use R programming language and 
the read.csv() function, which is a base R function for reading CSV files.

```{r code2, echo=TRUE}

# Section 2: Reading the data into R

data <-
read.csv("https://raw.githubusercontent.com/fivethirtyeight/data/b420a42e210b08d036467a481a
af404180979f3f/bad-drivers/bad-drivers.csv")

```{r code3, echo=TRUE}

# Section 3: Clean the data

# Renaming columns
colnames(data) <- c("State", "Number of drivers involved in fatal collisions per billion miles", 
"Percentage Of Drivers Involved In Fatal Collisions Who Were Speeding", "Percentage Of 
Drivers Involved In Fatal Collisions Who Were Alcohol-Impaired", "Percentage Of Drivers 
Involved In Fatal Collisions Who Were Not Distracted", "Percentage Of Drivers Involved In 
Fatal Collisions Who Had Not Been Involved In Any Previous Accidents", "Car Insurance 
Premiums ($)", "Losses incurred by insurance companies for collisions per insured driver ($)")

```{r code4, echo=TRUE}

# Section 4: Characteristics of the data

# This dataframe has 51 rows and 8 columns. The names of the columns and a brief description 
of each are in the table below:

library(knitr)
# Create a data frame with column names and descriptions
column_names <- c("Column Name", "Description")
column_descriptions <- c("State", "The name of the state in the United States.",
 "Number of drivers involved in fatal collisions per billion miles", "The number of 
drivers involved in fatal collisions per billion miles driven in each state.",
 "Percentage Of Drivers Involved In Fatal Collisions Who Were Speeding", "The 
percentage of drivers involved in fatal collisions who were speeding in each state.",
 "Percentage Of Drivers Involved In Fatal Collisions Who Were AlcoholImpaired", "The percentage of drivers involved in fatal collisions who were alcohol-impaired in 
each state.",
 "Percentage Of Drivers Involved In Fatal Collisions Who Were Not Distracted", 
"The percentage of drivers involved in fatal collisions who were not distracted in each state.",
 "Percentage Of Drivers Involved In Fatal Collisions Who Had Not Been Involved 
In Any Previous Accidents", "The percentage of drivers involved in fatal collisions who had not 
been involved in any previous accidents in each state.",
 "Car Insurance Premiums ($)", "The average car insurance premiums (in dollars) 
in each state.",
 "Losses incurred by insurance companies for collisions per insured driver ($)", 
"The losses incurred by insurance companies for collisions per insured driver in each state.")
column_data <- data.frame(column_names, column_descriptions)
# Print the table using kable
kable(column_data, align = "l")

```{r code5, echo=TRUE}

# Section 5:

# Selecting three columns
selected_columns <- data[, c("Number of drivers involved in fatal collisions per billion miles", 
 "Car Insurance Premiums ($)",
 "Losses incurred by insurance companies for collisions per insured driver 
($)")]
# Summary statistics
summary_data <- summary(selected_columns)
# Print the summary
summary_data
