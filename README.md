Use the given link and locate the bank marketing dataset. Data Set Link

Perform the below operations:
a. Create a visual for representing missing values in the dataset.
bank <- read.csv(file.choose(), sep = ";")
View(bank)
a <- table(is.na(bank))
library(Amelia)
missmap(bank, y.at = 1,y.labels = "",col=c("red","black"),legend = FALSE)

# there are no missing values in the dataset

b. Show a distribution of clients based on a Job.
library(ggplot2)
ggplot(bank,aes(job))+geom_bar()+
  ggtitle("Distribution of clients based on job")
  

c. Check whether is there any relation between Job and Marital Status?
# As per the chi sqaure test p value is less than 0.5 hence there is relation between Job and marital status


d. Check whether is there any association between Job and Education?
# As per the Chi square test p value is less than 0.5 hence there is association between job and marital status

tbl1<-table(bank$job,bank$marital)
tbl2<-table(bank$job,bank$education)
library(MASS)
chisq.test(tbl1)
chisq.test(tbl2)

	Pearson's Chi-squared test

data:  tbl1
X-squared = 3837.6, df = 22, p-value < 2.2e-16

> chisq.test(tbl2)

	Pearson's Chi-squared test

data:  tbl2
X-squared = 28483, df = 33, p-value < 2.2e-16



