# ECONOMETRICS EXAM 1 REVIEW (Ch1 - Ch5)



## Regression Problems



### step 1: Getting $\hat{\beta_{1}}$

$\hat{\beta_{1}}$ represents the slope parameter or the effect of change in explanatory variable on the independent variable.

###$\hat{\beta_{1}} = {\Sigma(x_{i} + \hat{x})(y_{i}-\hat{y}) \over \Sigma(x_{i} + \hat{x})}$

Note that $\Sigma$ will sum the multiples of two parts.

###$let \ \hat{\beta_{1}} = 0.5$



### step 2: Getting $\hat{\beta_{0}}$

$\hat{\beta_{0}}$ represents the intercept parameter. Given the slope intercept form of the independent variable we can use algebra to derive this.

###$\hat{\beta_{0}} = \bar{y}-\hat{\beta_{1}}\bar{x}$

###$let \hat{\beta_{0}} = 0.2$



### Step 3: Rewrite the Equation with calculated values

###$ y =  0.2 + 0.5x $

If x changes by 1, y changes by 0.5

---

## Coefficient Relations
---

### Actual Relation
###$y = \beta_{0} + \beta_{1}x$

For $1 \ unit$ change in x, y changes by $\beta_{1}$ unit

### Semi-Log Relation
###$\log_{}(y) = \beta_{0} + \beta_{1}x $

For $1 \ unit$ change in x, y changes by $\beta_{1} \times 100\%$

### Logarithmic Relation
###$\log_{}(y) = \beta_{0} + \log_{}(\beta_{1}x)$

For $1\%$ change in x, y changes by $\beta_{1} \times 100\%$

---
## STATA output interpretation and Hypothesis Testing
---
### Setting up null and alternative hypothesis

###$H_{0} : \hat{\beta} = 0.0$

The Null Hypothesis states that $x$ which has $\beta$ as the coefficient is independent of or irrelevant to y. If the null hypothesis is accepted, than we know that y is independent of x, thus we can disregard x. Note that leaving the x in the regression will not result in unreliable model because x does not effect y value. However we will experience higher variance.

###$H_{a} : \hat{\beta} \neq 0.0$

This is two tailed hypothesis testing. The Alternative Hypothesis states that $x$ which has $\beta$ as the coefficient is relevant to y. 

### Utilizing the STATA output for Hypothesis Testing

For a explanatory variable to be relevant, we need to reject the null hypothesis. To do that, we need the following to be true :

**t > df @ confidence interval**

or

**p < significance level**

These two are equivalent statements.

For STATA, confidence interval is set to 95% by default, and our alternative hypothesis is assumed to be two tailed. Thus depending on the size of your sample we need to look at 95% interval. For our STATA output in class we had over 120 df, so we will use df = $\infty$ at 0.5.

Check if the t values are greater than this value. For df = $\infty$ at 0.5, the value is 1.960. Our t value for $educ$ is 10.83, for $exper$ it is 3.86. So we know to **reject the null hypothesis**.

For $age$ and $age^2$ we see the t values are smaller than 1.960. So we accept the null hypothesis for those two and disregard them.

Other way is to use the P > |t| value. Since our significance level is set to 5% by default, the P value must be less than 5% or **0.05**

For both of $educ$ and $exper$ we see the P value is 0.000. So we reject the hypothesis. For both $age$ and $age^2$ we can see the p value is greater than 0.05. So we accept the null hypothesis.

---
## Terms, Assumptions, and Theorems
---

CURRENTLY EDITING . . .