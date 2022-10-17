# LSL-coding
an introduction to statistical learning with applications in R

#charpter three linear regression

#simple linear regression

#build regression medv is result, and lstat is predictor
```
lm.fit <- lm(medv ~ lstat, data = Boston)
```
#show the result of this regression, including residuals\coefficients\signif
```
summary(lm.fit)
```
#see the categary of summary
```
names(lm.fit)
```
#concrete factor
```
coef(lm.fit)
confint(lm.fit)
```
#function
```
predict(lm.fit,data.frame(lstat = (c(5,10,15))),
        interval = 'confidence')
predict(lm.fit, data.frame(lstat = (c(5,10,15))),
        interval = 'prediction')
```
#draw multiply picture in one part
```
par(mfrow=c(2,2))
plot(lm.fit)
```
#compute the residuals and studentized residuals
```
residuals(lm.fit)
rstudent(lm.fit)
```
#multiple linear regression
#build regression
```
lm.fit <- lm(medv ~ lstat + age, data = Boston)
```
#the pattern is lm(y ∼ x1 + x2 + x3)
#if you want to contain all variables
```
lm.fit <- lm(medv ~ ., data = Boston)
```
#interaction terms
#lstat:black, tell R to include an interaction term between lstat and black
#lstat * age, simultaneously includes lstat,age and the interaction term lstat and age

#non-linear relationship
#we can use I()to construct
```
lm.fit2 <- lm(medv ~ lstat + I(lstat^2)
```
#test the efficient of two functions, the anova() function performs a hypothesis
#test comparing the two models, the null hypothesis is that the two models fit the data
#equally well, and the alternative hypothesis is that the full model is superior
```
anova(lm.fit, lm.fit2)
```
