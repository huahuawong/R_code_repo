Review this for reference: https://rpubs.com/dataguru/316880

```
Key questions: Q3 and Q4
```

Takeaways from this chapter is to pay attention to the number of predictors and number of samples available. And also the distribution of the samples.

If the number of samples is largely greater than the number of predictors, it is visible to split the dataset into training and test set, this will enable the evaluation of model performance and tuning parameter selection.

For Q3:
The “one-standard error” method for choosing simpler models ﬁnds the numerically optimal value and its corresponding standard error and then seeks the simplest model whose performance is within a single standard error of the numerically best value

Another thing to add is to utilize data resampling techniques to make sure the distribution of each class is (almost) even.
