## Linear regression

Linear regression assumes a linear or straight line relationship between the input variables (X) and the single output variable (y).

More specifically, that output (y) can be calculated from a linear combination of the input variables (X). When there is a single input variable, the method is referred to as a simple linear regression.

In simple linear regression we can use statistics on the training data to estimate the coefficients required by the model to make predictions on new data.

The line for a simple linear regression model can be written as:
```C++
    y = b0 + b1 * x
```
where b0 and b1 are the coefficients we must estimate from the training data.

Once the coefficients are known, we can use this equation to estimate output values for y given new input examples of x.

It requires that you calculate statistical properties from the data such as mean, variance and covariance.

All the algebra has been taken care of and we are left with some arithmetic to implement to estimate the simple linear regression coefficients.

Briefly, we can estimate the coefficients as follows:
```C++
    B1 = sum((x(i) - mean(x)) * (y(i) - mean(y))) / 
         sum((x(i) - mean(x))^2)
    B0 = mean(y) - B1 * mean(x)
```

* Calculate Mean and Variance
```C++
    mean(x) = sum(x) / count(x)
    variance = sum((x - mean(x))^2)
```
* Calculate Covariance
```C++
    covariance = sum((x(i) - mean(x)) * (y(i) - mean(y)))
```
* Make Predictions
```C++
    y = b0 + b1 * x
```

