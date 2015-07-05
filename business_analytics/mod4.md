# Mod 4 Single Variable Linear Regression

## 4.1 Introduction

## 4.2 The Regression Line

To perform correlations in excel use the following function
```
CORREL(ARRAY1, ARRAY)
```

### 4.2.3 The structure of the regression line

+ Best Fit line from sample data:  y&#770; = a + bx 
+ "True" Best Fit Line from all population data: y&#770; = &alpha; + &beta;x
+  y = &alpha; + &beta;x + &epsilon; 
 + &epsilon; = y - y&#770; or the error in the estimation


## 4.3 Forecasting

Should only feel comfortable forecasting when data is within historical ranges.

Another quick way to forecast is to use Excel’s FORECAST function:
```
=FORECAST(x, known_y’s, known_x’s)
```

### 4.3.2 Predicition Interval

Point Forecast - Single Values, however since regression line is an estimate, and we also get less accurate as we forecast values towards the end of our range. 

Rather than predict a single point, we construct a point forecast or a range around the point forecast where there isa high probability for the point to exits.

The prediction interval is normally distributed and centered around the point forecast. This is analogous to confidence interval. 

Standard error of regression is found in regression output table and is conservative estimate of the standard deviation of the prediction interval.

As we move towards the edge of the data, the width of the prediction interval widens.


### 4.3 Summary
```
=SUMPRODUCT(array1, [array2], [array3],…) is a convenient function for calculating point forecasts.
```

## 4.4 Interpreting Regression Output 

_Residual Error_ - The distance between regression line and data point.

Regression line is line that reduces the sum of squared residual errors. This is least squares optimization.

Question: How much more accurately does regression line help us predict price than price alone.

*Answer*: Take the mean price and create a line. this is the mean price line. calculate the sum of squared residual errors for this line. This sum is the the total sum of squares error and substract the residual sum of squares.  The result is the rgression sum of squares.

**Regression Sum of Squares** - The Variation explained by the regressin line.  

**Residiual Sum of Squares** - The variataion unexplained by regression line.


R-squared - Measures how closely a regression line fits a data set. 
 + R<sup>2</sup> = Regression Of Sum of Square/ Total Sum of Squares.
  + 0 means regression explains nothing, 1 means regression explains all of variation.

R - known as correlation coefficient.

### 4.4.2 Testing for a Significan Relationship

To check whether there isn't a relationship, check whether a slopes regression line has a slope of zero.
 + You can check that the 95% confidence range for the slope contains 0 
 + Check whether the p value is greater than 0.05

### 4.4.3 R-squared vs p value

### 4.4.4 Residual Analysis

Take the residuals and plot them.  The resulting distribution should be normally distributed with same variances, it should appear random.  If there is a pattern amongst residuals that indicates that linear approximation might not be best fit.

heteroskedasticity - when the residuals terms vary with one or more of the indepent variables.  when the is a correlation between error and a variable.


## 4.5 Performing Regression Analysis 

### 4.5.1 Performing Regression Analysis in Excel
Step 1

## 4.6 Forecasting Home Video Units.

From the Data menu, select Data Analysis, then select Regression. 

Step 2

Enter the appropriate Input Y Range and Input X Range:

The Input Y Range is the dependent variable, in this case selling price. The data are in column C with its label, C1:C31.
The Input X Range is the independent variable, in this case house size. To ensure the independent variable is labeled correctly in the output table, enter the data with its label in column B, B1:B31.
Since we included the cells containing the variables’ labels when inputting the ranges, check the Labels box.
We have already entered E1 as the output range.
Step 3

Scroll down and make sure to check the Residuals and Residual Plots boxes to ensure we see the relevant residual information. (Note that you will not be able to submit if you do not include the residual plot.)


### 4.5.2 Using Dummy Variabels
Using Dummy Variables 1 and 0 the expected value using regression is the same as using the conditional mean.


## 4.6 Forecasting Home Video Unitsl

