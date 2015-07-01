# Module 5 - Multiple Regression
## 5.1 Introduction
### 5.1.1 Multiple Regression at Caesars

How would you predict number of checkins
+ Season Pattern
+ Day of Week
+ Big Convention/Boxing

## 5.2 the Multiple Regression Equation
### 5.2.1 Single vs. Multiple Regression

Use 1 variable vs uses multiple variables.

Note: The r-squared values of the two single variable regressions do not add up.  This is because the variables themselves might also have a correlation for example, distance from a major city and house size. 
 + In Boston example houses are small and cheaper as you move away from Boston.

Multiple regression separates the effect of the correllation of the independent variables.
 + In the multiple regression the coefficient for house size is set for controlled distance, and visa-versa. 



Gross Relationship - The gross effect on independent variable on a dependent variable. May pick up effect of other factors not in model. 

Net Relationship - The net effect controls for all other factors (independent varibles) included in the model.  
 + Coefficients in multiple regressions are net with respect to variables included in model, and gross with respect to omitted variables.

## 5.3 Adapting Concepts From Single Regression
### 5.3.1 Adjust R-squared

R^2 is 100% if number of data points = number of independent variables + 1.
Module is overdetermined by only 1 row so we can can find exact line or planeto fit points.

Adjustment factor - Reduces R^2 by each independed variable added to the module.
 + Its critical to use adjusted r-squared when comparing regressions with differnt numbers of variables.
 + In the Boston home price case the adjusted r-squared is greater than either of the r-squared in the single var cases. This indicates we've gained explanatory power by using two variables.

### 5.3.2 Residual Analysis

With multivar regression you plot the residuals for each variable on seperate plots.

### 5.3.3 Testing for Significance of Variables

As with single variable regression look at the p values, and the standard errors.


## 5.4 Performing Multiple Regression Analysis
### 5.4.1 Multiple Regression Analysis in Excel
