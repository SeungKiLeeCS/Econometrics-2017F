# Homework 3

``` 
Seung Ki Lee
Chatper 7 : Q2 (i, ii, iii, iv)
```

### i) 

​	The birthweight decreases by 0.44% per cigarrete smoked. For 10 cigarette smoked per day, the birth weight will decrease by 4.4%.

### ii)

​	Holding all other factors constant, a white child will be 5.5% heavier in birth weight. 

To see the difference is statistically significant, the t-statistic on $white$ is $0.055 \over 0.013$ = $4.23$. Given our alpha value = 5%, and with degree of freedom n-k-1 = n-6 = 1382.  1382 > 120, so we have c = 1.960. 

t < c we accept null hypothesis, and if t > c we reject null hypothesis.

4.23 > 1.96, thus we reject the null hypothesis that $white$ is an insignifcant variable, and this difference is statistically significant.

### iii)

​	Per unit of education of the mother, the birthweight changes by a 0.3%. 

Again to see the difference, t-statistics $0.0030 \over 0.0030$ = $1$. The degree of freedom here is n-k-1 = n-7-1 = n-8. 1183 > 120 so we have c = 1.960.

1 < 1.96, thus we accept the null hypothesis that $mothereduc$ is statistically insginificant

### iv)

​	Computing F-Statistic requires two regressions in use to have same sets of observations. With sample size of the first regression being greater than that of the second, we can predict that the dataset we have is missing some observations of $mothereduc$ and $fathereduc$. And because these two regressions have sample sizes we are unable to compute F-statistic. If we wanted to do this we will have to estimate the first regression again with adjusted 1191 observations to match that of second regression and compute a new $R^2$.