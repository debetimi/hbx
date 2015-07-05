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
Same as single var.


### 5.5.1 Multicollinearity

**Multicollinearity** - Multicollinearity occurs when two independent variables are so highly correlated that it is difficult for the regression model to separate the effect each variable has on the dependent variable. 

Usually not an issue if only using regression for predictions.

If a variable that was significant because insignificant when added to another analysis.  Then that means there is some collinearity, meaning there is a corellation between that variable and other variable.
 + For example in the Boston example, if you add lot size, the lot size is not significant.
 + However, the lot size does improve the R^2

When dealing with collinearity, one has to decided wether or not to remove coliner variables. In the house price, we would prefer to keep lot size because lot size should have an effect on house price that is different from house size even though they are related.

### 5.5.2 Dummy Variables
When assigning dummy variables you have to have 1 fewer than the number of options in the category.  For example days of the week, you can have at most 6 dummy variables.

### 5.5.3 Lagged Variables

Lagged Variables - Sometimes the effect of a variable from a previous year affects the dependent variable of this year.  Using this u can add a lagged value.  However by doing this you have to reduce the number of observations you can use because the first row wont have a lagged value.

