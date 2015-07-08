# Mod 1 - Describing and Summarizing Data

## 1.2 Visualizing Data
### 1.2.3  Outliers

An _outlier_ is a x value such that is x < Q<sub>1</sub> - 1.5&times;IQR or  x > Q<sub>3</sub> - 1.5&times;IQR
 + Q<sub>1</sub> is 1st Quartile
 + Q<sub>3</sub> is 3rd Quartile
 + IQR is Inner Quartile Range, Q<sub>3</sub> - Q<sub>1</sub>

## 1.3 Descriptive Statistics

### 1.3.1 Central Values for Data

_The central tendency_ is the indication of where  the center of a data set lies.  

There are three metrics commonly used as a central tendency
+ Mean - Average 
+ Median - Middle Value
+ Mode - Most Common Value 

Excel:
```
=AVERAGE(number1, [number 2],...)
=MEDIAN(number1, [number 2],...)
=MODE.SNGL(number1, [number 2],...)
```

### 1.3.2 Conditional Means

Average a value only if some criteria is met
```
=AVERAGEIF(range, criteria, [average_range])o
```

### 1.3.3 Percentiles
Find a the value at the the kth percentile of a given set of values.
```
=PERCENTILE.INC(array, k)
```

### 1.3.4 Variability

The range is defined as Maximum Values - Minimum Value

Variance - The the average of the sum of the squared differences of the values in set from the mean. Variance measures how far a set of numbers is spread out. Units are squared units of the set.

Standard Deviation - Sqrt root of the variance in same unit as mean. Measures the spread in set of values or distribution.

Excel
```
=VAR.S(number 1, [number 2], …)
=STDEV.S(number 1, [number 2], …)
```

### 1.3.6 Coefficient of Variation

The _Coefficient of Variation_ allows you to compare variablity in two different sets of data.

Coefficient of Variation = Standard Deviation/Mean

Excel
```
=CORREL(array1, array2)
```

## 1.4 Relationships between Two Variables.

Corellation coefficiation is a meausure of correlation between two variables. A correlation of 0.75 or greater is usually considered sufficient.

### 1.4.3 Hidden Variables

Often times there is a hidden variable causing correlation.  For example, tank tops sold and ice cream bars sold are positively correlated, but the actual variable they are dependent on is the weather.
