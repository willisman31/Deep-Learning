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

- 
