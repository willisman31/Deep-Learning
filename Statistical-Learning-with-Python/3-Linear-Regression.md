# Linear Regression

- supervised learning mecahnism for predicting quantitative response

## Simple Linear Regression

- predict quantitative result *Y* using a single predictor *X*
- assumes a roughly linear relationship between *Y* and *X*
- ![image](../.images/simple-linear-regression-equation.png)
    - "we are regressing *Y* onto *X*"
    - ![image](../.images/nuclear-linear-regression-expression.png)
        - estimation for a single instance
    - in this equation we're just trying to find the values of slope and intercept

### Estimating the Coefficients

- given a set of training predictors and outcomes, we aim to estimate the values of $\hat{\beta}_{0}$ and $\hat{\beta}_{1}$- the intercept and slope, respectively
- least squares = the most common mechanism for measuring *closeness*
- residual = difference between *i*th observed and predicted response
- residual sum of squares (RSS) = measure of fitness for a model to a set of data
    - ![image](../.images/rss-equation-1.png)
    - ![image](../.images/rss-equation-2.png)
    - optimal models minimize the RSS
        - ![image](../.images/least-squares-coefficients-estimates-equation.png)
        - the above are the equations for estimating least squares coefficients
        - $\bar{x}$ and $\bar{y}$ are the sample means

### Assessing the Accuracy of the Coefficient Estimates

- if *f* can be approximated by a linear function, it takes the form: ![image](../.images/linear-function-with-error.png)
    - error term may be "working harder" in some instances based on the true form of *f*
- population regression line = closest estimation of *Y* relative to *X*
    - unobserved in practice; always the same for a given problem space
- least squares line = $\hat{y}$; or predicted set of values
    - based upon training data, thus differs between training sets
- the average of least squares lines across all possible samples will be exactly equal to the population regression line
    - this property aligns with the lack of bias in the method
    - while the average will eventually align, any given least squares line may be a great over/underestimate of the population regression line -> **Standard Error**
- standard error = average amount by which an estimate differs from its actual value
    - ![image](../.images/standard-error-linear-regression.png)
    - $\sigma$ = standard deviation of each $y_{i}$
        - not known, but can be estimated from data
        - residual standard error (RSE) = estimate of $\sigma$; ![image](../.images/rse-equation.png)
    - used to compute confidence intervals
        - confidence interval = range in which we can assign a certain probability that true value will be contained within
---
left off at hypothesis tests on p76