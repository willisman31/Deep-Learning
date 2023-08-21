# Statistical Learning

## What is Statistical Learning?

- input variable = predictor = independent variable = feature; denoted with *X*
    - number of predictors is indicated using *p*
    - *n* = number of observations
- output variable = response = dependent variable; denoted with *Y*
- error term $\epsilon$ = variable value which is added to a function describing the relation between *X* and *Y* and which averages to 0; the variable itself may change depending on the input data
    - ex. *Y* = *f*(*X*) + $\epsilon$
    - goal is to estimate function *f* using known observations
    - statistical learning = estimating *f*

### Why Estimate *f*?

2 reasons:
    1. prediction
    2. inference

#### Prediction

- $/hat{Y}$ = $/hat{f}$(*X*)
    - $/hat{Y}$ is the predicted response
    - $/hat{f}$ is the predicted function
    - $/hat{Y}$'s accuracy is dependent upon 2 variables:
        1. reducible error - error that is introduced by having an imperfect estimate of *f*
        2. irreducible error - error that is introduced by $\epsilon$; this error may arise from missing predictors or unquantifiable variations
            - the upper bound on prediction accuracy
            - value is unknown in practice

#### Inference

- if our goal is to determine the relationship between *X* and *Y*, then *f* cannot be treated as a black box- its form must be known because we are not interested in $/hat{Y}$
- the following questions may be asked in this case:
    - which predictors effect *Y*?
    - how do relevant predictors effect *Y*?
    - is the relationship between relevant predictors and *Y* linear or more complicated?
- linear models make it easier to interpret relationships between predictors and responses
- nonlinear models often make more accurate predictions based on inputs, but make interpretation of relationships more difficult (more black box approach)

### How Do We Estimate *f*?

- all models require a set of *n* inputs (training data)
- *x_{ij}* = value of *j*th predictor of *i*th observation
- *y_{i}* = value of *i*th prediction
- goal is to find $/hat{*f*}$ that most accurately predicts *Y*; methods for this can broadly be defined as parametric or non-parametric

#### Parametric Methods

- 2-step model-based approach:
    1. assume shape/form of the relationship
        - ex. relationship is linear, which simply means that coefficients applied to predictors must be manipulated to find $/hat{f}$
    2. follow procedure to fit/train the model to reflect the assumed relationship
        - least squares is the most common method for a linear model, but many others exist
- reduces the effort of modeling down to selecting the right coefficients
- advantages:
    - easier to fit coefficients to a known (or assumed) relationship than it is to try to determine the relation based on limited data
        - trying to determine the form using limited data will often lead to overfitting, where the model is too closely trained to the $\epsilon$ of the training data
- disadvantages:
    - if our assumption about the form is incorrect, then resultant estimates will be low quality
- with limited data, a parametric approach is often the best option

#### Non-Parametric Methods

- makes no assumptions about the form of *f*
- requires much more data to achieve an accurate estimate than does the parametric method
    - overfitting is extremely likely with low quantities of observations; new observations will likely not be predicted accurately by these models in this case

### The Trade-Off Between Prediction Accuracy and Model Interpretability 

- As model flexibility increases, interpretability decreases
- If you need to determine the relationship between predictors and responses (e.g. how television advertisements affect voter sentiment) then using a highly inflexible model would make sense
    - conversely, if you only need to make predictions, then it doesn't really matter whether you understand the relationship, so a more flexible model (assuming sufficient input) would be better

### Supervised Versus Unsupervised Learning

- supervised learning involves both an input and an output
- unsupervised learning focuses on understanding the relationships between various predictors
- semi-supervised learning is a combination of the two that occurs when only a subset of responses for observations are available (e.g. when collecting responses is more costly than collecting observations)

### Regression Versus Classification Problems

- problems that involve quantitative responses are regression problems
- problems with qualitative responses are classification problems
    - most stat learning methods can be applied to a situation so long as their predictors are properly coded
- some overlap may exist especially when data have binary classes

## Assessing Model Accuracy

- there is no single greatest model, different models will perform better on different data sets

### Measuring the Quality of Fit

- each predicted response in a supervised model must be evaluated in terms of its accuracy relative to the actual response
    - common mechanism used for this is *Mean Squared Error* (MSE)
    - ![image](../.images/mse-equation.png)
    - when a model is good/accurate, the MSE will be small
- the accuracy of the model relative to the training data is unimportant- if it was, then models would be optimized to fit data rather than their underlying patterns
    - test data is used to assess accuracy
    - prediction accuracy against training data is not necessarily indicative of accuracy against test data
- training MSE will decrease with greater model flexibility
    - when a less flexible model would have yielded a lower test MSE, we see overfitting in action

### The Bias-Variance Trade-Off

- expected test MSE can be decomposed into the sum of 3 values:
    1. variance of f-hat
    2. squared bias of f-hat
    3. variance of $\epsilon$
- ![image](../.images/expected-test-mse.png)
    - the overall expected test MSE can be determined by averaging the result of this equation across all test values
    - to minimize expected test error, lower *bias* **AND** lower *variance*
- variance = how different f-hat would be if a different training set was used
    - higher variance typically results from higher flexibility
    - ideally, different training sets should yield the same f-hat
- bias = error resulting from attempting make a prediction about a complicated phenomenon using an overly simplistic model
    - more flexible models result in lower bias
- when determining the flexibility of a model, we want to find a balance between bias and variance that lowers the test MSE
    - the rates of change of bias and variance relative to model flexibility are not the same, which is what makes a single optimal balance possible
- finding a balance to this trade-off is a central goal in statistical learning problems
- explicit computation of test MSE isn't practically possible because the true value of *f* is virtually never known

### The Classification Setting

- 
