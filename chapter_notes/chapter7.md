# Econometrics Class Notes

# Chapter 7 : Qualitative Info

2017/10/17

## Review

---

Z Score : Used to compare which independent variable has greater impact on dependent variable $\hat{y} \over \sigma_{y}$

## Quadratic Form

---

It is more difficult to interpretate the impact of a explanatory variable if we use quadratic form rather than linear form.

## Qualitative Variable (Dummy Variable)

---

In the regression a dummy variable is always a boolean value of [0,1]. It usually represents a qualitative trait and thus immeasurable.

### Example

### $wage = \beta_{0} + \delta_{0}female + \beta_{1}educ + u$

here, the $\delta_{0}$ is the coefficient of the dummy variable $female$. The value of this variable is binary for given regression. With the qualitative variable, it is easy to keep everything else constant while changing one specific quality to see the difference in independent variable. [In this case, easier to observe the difference in wage between men and women]

### Dummy Variable Trap

Sometimes we have more than one dummy variable, but the problem comes when those two qualitative variables show perfect colinearity. If we have $male$ on top of $female$ in the above regression it will result in perfect colinearity as if female = 0, male is always = 1 and vice versa.



## Multiple Degrees of Qualitative Variable

---

2017/10/19



If we want to have varying degrees of Qualitative Variable and not a binary value we must **One Hot Encode** the set of qualitative variables. You do this by assuming one degree of qualitative variable is always 0 unless all other qualitative variables are 0. You can refer to this as base case. The assumption must stand where 1. all qualitative variables have binary value, 2. only one qualitative variable can be 1 in a single regression, and 3. every qualitative variables are zero indexed[it starts at 0, not 1]. Choose a **base case** and writing out everything else in the regression. It goes like this.

### $wage$ = $smart_{1} + smart_{2} + smart_{3}$

Lets assume that your wage only depends on your "smartness" which cannot be measured quantitatively. In this case your base case is $smart_{0}$=$1$. That is if $smart_{1} + smart_{2} + smart_{3}$ = $0$

In any case, only 1 out of 4 possible $smart$ values can be 1 at a time.



[Back to Contents](../SUMMARYhtml.html)