# Dana.Portfolio

Project Title: Medical School Admissions Interview locations K-mean Clustering Anaysis 

This project involves using K-means clustering to analyze the academic metrics of students attending on-campus interviews for medical school admissions. The goal is to identify distinct groups or types of students based on their academic profiles, which include factors such as GPA, standardized test scores (e.g., MCAT), and other relevant academic performance indicators. By applying K-means clustering, the analysis groups students into clusters with similar characteristics, allowing for insights into patterns or trends among those who tend to attend interviews. The results can help admissions committees better understand the diversity of applicants and refine their selection criteria based on academic data. This approach provides a data-driven way to segment applicants, offering a clearer picture of the types of students most likely to engage with the admissions process through interviews.

```{r}
library(tidyverse)
library(janitor)

setwd("C:\Users\danabr\Documents\R Projects")

intdf <- read.csv("Interviews 2022-2024.csv")
View(intdf)

summarize (intdf, n())

mean (intdf$UG.Cumulative.Non.Science)
mean (intdf$UG.Cumulative.Science)
mean (intdf$MCAT.Total)

options(scipen=+500000)
ggplot (data = intdf) + 
  geom_histogram(mapping = aes(x=MCAT.Total), binwidth = 1)
ggplot (data = intdf) + 
  geom_histogram(mapping = aes(x=UG.Cumulative.Non.Science), binwidth = 1)
ggplot (data = intdf) + 
  geom_histogram(mapping = aes(x=UG.Cumulative.Science), binwidth = 1)


tabyl(intdf$Sex)
tabyl(intdf$State)
tabyl(intdf$Int.Location)
tabyl(intdf$County)
