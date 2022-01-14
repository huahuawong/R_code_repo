### 8.1
(a) Fit a random forest model to all of the predictors, then estimate the variable importance scores:
```
model1 <- randomForest(y ~ ., data = simulated, importance = TRUE, ntree = 1000) 
rfImp1 <- varImp(model1, scale = FALSE)
rfImp1
```

No, the predictors V6-V10 have very small importances as compared to the other predictors

(b) Now add an additional predictor that is highly correlated with one of the informative predictors. For example:
```
simulated$duplicate1 <- simulated$V1 + rnorm(200) * .1
cor(simulated$duplicate1, simulated$V1)
```

Fit another random forest model to these data. Did the importance score for V1 change? What happens when you add another predictor that is also highly correlated with V1?

We can see that there is a dip in importance score.  This is because the trees in the random forest are just as likely to pick V1 for a split than to pick duplicated1, since they are very correlated. As a result, the total number of splits that originally belonged to V1 is “shared” with duplicated1.

(c) Use the cforest function in the party package to fit a random forest model using conditional inference trees. The party package function varimp can calculate predictor importance. The conditional argument of that function toggles between the traditional importance measure and the modified version described in Strobl et al. (2007). Do these importances show the same pattern as the traditional random forest model?

Similar patterns can be observed.


### 8.2 Use a simulation to show tree bias with different granularities.
Predictors with higher number of distinct values are favoured more over granular predictors also referred as selection bias in tree based models. However if the data contains noise variables, they are favored over the low variance predictors. With the increase in noise in the data, the chances of selection of granular predictor increases. 

### 8.3
Refer to https://rpubs.com/azureblue83/488996
