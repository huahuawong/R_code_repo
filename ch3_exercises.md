### 3.1. The UC Irvine Machine Learning Repository contains a data set relatedto glass identiﬁcation. The data consist of 214 glass samples labeled as oneof seven class categories. There are nine predictors, including the refractiveindex and percentages of eight elements: Na, Mg, Al, Si, K, Ca, Ba, and Fe.


(a) Using visualizations, explore the predictor variables to understand their distributions as well as the relationships between predictors?
```
# For the R1 column, repeat for the other columns 
par(mfrow=c(2,3))
hist(Glass$RI,breaks=10, col=brewer.pal(10,"Set3"),main="R1")

# Find correlation between predictor variables
cor(Glass$Mg, Glass$Si, method="pearson")

```

(b) Do there appear to be any outliers in the data? Are any predictors skewed?
```
# Check for outliers
# First let's check summary of a column
summary(Glass$Na)

# Next let's try box-plots
boxplot(Glass$Na,
        ylab = "Na"
)


# We can see that there are some potential outliers, about 6 of them, we can use statistical testing to test that (Grubbs’s test, Dixon’s test, Rosner’s test)
library(outliers)
test <- grubbs.test(Glass$Na)
test <- grubbs.test(Glass$Na, opposite = TRUE)


# Check Skewness
library(e1071)
skewness(Glass$RI)
```

(c) Are there any relevant transformations of one or more predictors that might improve the classiﬁcation model?
```
# we can use box-cox transformation here to transforms our data so that it closely resembles a normal distribution
```


### 3.2 and 3.3
A very good reference: https://rpubs.com/fraki22/122619
Another one: https://rpubs.com/Bissoli/APMchapter3
