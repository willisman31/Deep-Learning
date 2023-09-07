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
---
## THIS HERE IS IMPORTANT ##

- ![image](../.images/least-squares-coefficients-estimates-equation.png)
- the above are the equations for estimating least squares coefficients
- $\bar{x}$ and $\bar{y}$ are the sample means
---
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
- hypothesis test = binary test between a null hypothesis and an alternative hypothesis
    - ex. $H_{0}$: there is no relationship between *X* and *Y*; $H_{a}$: there is some relationship between *X* and *Y*
        - in effect, with regard to linear regression, we're asking is $\beta_{1}$ equal to 0
    - practically, *t-statistic* is calculated to determine the ratio of standard error to our estimated value's difference from our null hypothesis value
        - i.e. t-stat = how many times our standard error is the difference between our estimate and our null hypothesis value
        - using the t-stat, we can calculate the p-value
            - p-value = correlatory value that suggests whether we should reject/accept our null hypothesis
        - ![image](../.images/t-stat-equation.png)

### Assessing the Accuracy of the Model

- quality of fit for a linear regression model is determined using 2 related values:
    - residual standard error (RSE)
    - $R^{2}$ statistic

#### Residual Standard Error

- RSE = estimate of standard deviation of $\epsilon$; measure of *lack* of model fit- higher values = lower fit
    - measured in units
- ![image](../.images/rse-formula.png)
    - ![image](../.images/rss-equation-3.png)

#### $R^{2}$ Statistic

- measured as a proportion between 0 and 1
    - independent of scale
- ![image](../.images/r-squared-statistic-equation.png)
    - TSS = total sum of squares; amount of variability in *Y*; ![image](../.images/tss-equation.png)
    - RSS = unexplained variability within linear regression model
- $R^{2}$ = how much variability in *Y* that is explained by *X*
    - higher values mean that more variation is explained by the regression
- correlation = ![image](../.images/correlation-definition.png)
    - squared correlation and $R^{2}$ statistic are identical in simple linear regression models
    - correlation is not exactly useful in complex settings because it is limited to comparing a set of just two variables -> this is the importance of the $R^{2}$ statistic

## Multiple Linear Regression

- when trying to predict a value on the basis of multiple input features and using linear regression, a single unified model must be created to simultaneously utilize the effects of all input features
- ![image](../.images/multiple-linear-regression-model.png)

### Estimating the Regression Coefficients

- as was the case with simple linear regression, we're trying to estimate the coefficients for the above equation 
- 