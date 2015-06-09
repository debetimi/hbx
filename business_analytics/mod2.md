# 2 Sampling and Estimation

## 2.1 Introduction
Often we wish to analyze a large set of people

- Population: The set
- Members: The people or objects in set.

Due to time or resources we often can't analyze all the members of the population so we analyze a *sample*. A subset that is representative of the entire set

## 2.2 Sampling

### 2.1.1 Sampling at Amazon
From the Amazon case we can see that sample is a lower cost way to glean information about statistics of interest. It is expensive in cost and time to gather information for every single point of data.

### 2.2.1 Samples vs. Populations
Before we take a sample we need clear understanding of problem we need to address based on that understandng we do things:

1. Select correct target population to sample.
2. Determine the question we want to ask about that sample

**Key Point**: To obtain a representative sample we need to choose the people at random otherwise there will be sample bias.

Sample Cycle:

1. Select correct target population
2. Sample the population
3. Analyze the results
4. Draw Conclusions about the population

The numerical properties of populations are called parameters and those of a sample are called statistics.  A statistic is an estimate of a true value of a paramters.  The larger the sample the more accurately statistics predict parameters.

|     | Mean | Standard Deviation |
| --- |:----:|:------------------:|
| Population (parameters) | &mu; | &sigma;|
| Sample (statistics)     | x&#772; | s |

#### Amazon
Uses software to randomly send employees to various shelves/type of shelves to check accuracy of inventory tracking system. The use statistics to figure out the smallest sample at the right frequency to figure out statistical significance of results.

### 2.2.2 Sample Size
In addition to deciding how to sample, we must also decide how large the sample should be.

Key Note: Sample size is _not_ indicative of sample quality meaning we don't have to sample a larger population in greater numbers than smaller population to get an accurate sample. Think about sampling the number of female employees at a company.  If the sample size is significant say 1000. It doesn't matter if the company is 20,000 or 200,000 because 1,000 is statistically significant.

A large sample size is useful if you are trying to detect something rare.

As you increase sample size, sample mean and std move closer to population mean and stdev.

### 2.2.3 Avoiding Bias
Avoid using leading languages or phrases.

 + Good: Is underage drinking acceptable?
 + Bad: Underage drinking is okay, right? This leads the respondent into agreeing with question.

Cononical Example: Politically charged words 

+ Does the government spend enough money on assistance to the poor. 64% Said too little
+ Does the goverment spend enough money on welfare. 19% said too little.

Response Rates

+ Low response rates often lead to bias if the non-responders represent a differnt segment of the population than the respondees.  If we have a low resrate we should contact non-respondents in order to increase the response rate or demostrate non-respondents do not respresent a different segment of the population

### 2.2 Summary
+ Make sure the sample is representative of the population by choosing members randomly to ensure that each member of the population is equally likely to be included in the sample.
+ Choose the right sample size:
 + Sample size does not necessarily depend on population size. The right sample size depends on desired accuracy and in some cases, the likelihood of the phenomenon we wish to observe or measure.

+ Avoid biased results by
 + Phrasing questions neutrally
 + Ensuring that the sampling method is appropriate for the demographic of the target population
 + Pursuing high response rates. It is often better to have a smaller sample with a high response rate than a larger sample with a low response rate.

## 2.3 The Normal Distribution
### 2.3.1 Rules of Thumb
+ Sample mean is just a single point. We call this a __*point*__ estimate. 
+ Sample mean doesn't give estimate of how accurate it estimates population mean  

Normal/Gaussian Distribution - Probablity distribution centered at the mean

 + To find the percentage of values between a certain range integrate the curve over those values.  Or take the area underneath the curve between those values.
 + Normal distributions are symetric so the mean is the median. P(< Mean) = 50%
 + The shape of curve, how flat or narrow it is, is determined by the standard deviation.
  + narrow: std dev is small so most values are very close to mean.
  + flat: std dev is large so values are spread out.
 + P(&mu;-&sigma;&le; x &le;&mu;+&sigma;) &asymp; 68%  
 + P(&mu;-2&sigma;&le; x &le;&mu;+2&sigma;) &asymp; 95%  
 + P(&mu;-3&sigma;&le; x &le;&mu;+3&sigma;) &asymp; 99.7%  
 + You can label x-axis using relative number of &sigma; away from mean using z values. z = (x-&mu;)/&sigma;

## 2.3.2 The Normal Function: NORM.DIST
+ Normal Distribution: `NORM.DIST(x, mean, standard_dev, cumulative)`
 + cumulative `true` means we want cumulative probabilty till x. `false` means we want the value of probability density or the height at x.
+ Standard Normal Distribution - &mu; = 0, &sigma; = 1; 
 + `NORM.DIST(x, 0, 1, cumulative)` OR `NORM.S.DIST(z, cumulative)`
 + z is the z-value we weant to evaluate. We can find z by using `z = STANDARDIZE(x, mean, standard_dev)` 
 + cumulative `true` means we want cumulative probabilty till x. `false` means we want the value of probability density or the height at x.

## 2.3.3 The Normal Function: NORM.INV 

Sometimes we want to find the value associated with a certain cumulative probabilty.  For example if we wanted to figure out what height was the 80th percentile in a distribution.

To do this we use the excel function `NORM.INV(probabilty, mean, std_dev)` 


### 2.3.4 The Central Limit Theorem

If we take many random samples from a population, and plot the means of each samples, the the distribution of the sample means will be a normal curve.  If we take enough random samples then the distribution of the sample means we will be centered at the population mean.  The difference between the distribution of sample means and the population is std deviation.  The &sigma;(distribution) = &sigma;(population)/&radic;n If our sample sizes are larger we will have a much narrower std deviation.

+ In practice, we take a single sample we don't take many random samples. But we can use sample without worrying about population because CLT tells us that the distribution of sample means part of a normal distrubution that is centered around the population mean. Meaning if we have significat number of points to allow for a low &sigma; we know we will be close to population mean.


## 2.4 Confidence Intervals

### 2.4.1 Estimating the Population Mean

With a normal distribution, we know that if we pick a random point there is 95% chance that the valuation is within 2 standard deviations of the standard deviation.

Applying This to Distribution of Sample Means

+ Take a sample and get the mean.  We know from CLT that the distribution of sample means is normal and centered at population mean, so this sample mean has a ninety 95% of being within 2 stdev's of the population. So our _Confidence Interval_ is 95% for +/- two standard deviations from our sample mean.
+ This means 5 percent of samples will **not** have confidence intervals that contain the population mean.

**Confidence Interval** = x&#772; &plusmn; z<sup>s</sup>&frasl;<sub>&radic;n</sub>

+ z is zalue for desired level of confidence
+ x&#772; is the sample mean
+ s is the sample standard deviation
+ n is the sample size

### 2.4.2 Large Samples
+ Large enough sample size is typically defined as greater than 30 data points.
+ To calculate the confidence norm using excel we can use `CONFIDENCE.NORM(alpha, standard_dev, size)`
 +  alpha, the significance level, equals one minus the confidence level (for example, a 95% confidence interval would correspond to the significance level 0.05).
 + standard_dev is the standard deviation of the population distribution. We will typically use the sample standard deviation, s, which is our best estimate of our population’s standard deviation.
 + size is the sample size, n.

 ### 2.4.3 Small Samples

If there are fewer than 30 data points then we cannot create _confidence interval_ because central limit theorem may not apply.

If the underlying data point is normal, however, we can construct interval using a modified approach.  Instead of using a z-distribution we can use a t-distribution.  The t-distribution looks similar but is not as tall in the center and has thinker tails.  This reflect that t distribution has a larger standard deviation.

**Confidence Interval T-distribution** = x&#772; &plusmn; t * s/&radic;n
+ In Excel we can use the function `CONFIDENCE.T(alpha, standard_dev, size)`
 + _Descriptive Statistics_ uses this function for confidence intervals

### 2.4.4. Choosing a Sample Size

Let say we wanted our margin of error to by 1kg/m^2 for our 95% confidence interval.  How do we select n to achieve a given margin of M?

z<sup>&sigma;</sup>&frasl;&radic;n &le; M &rightarrow; n &ge; (z<sup>&sigma;</sup>&frasl;<sub>M</sub>)<sup>2</sup>

However since we usually do not know &sigma;, the population std. dev, we will have to take a preliminary sample and use the sample's standard deviation instead.

n &ge; (z<sup>s</sup>&frasl;<sub>M</sub>)<sup>2</sup>

+ For a proportion, the confidence interval can be calculated using p&#772; &plusmn; z * (&radic;p&#772;(1-p&#772;))/&radic;n

#### Verifying Sample size for Low Probability Events
+ Lets say we dealing with something that has very small proportion like ALS which affects between 0.006% and 0.008% of people in US.  How can we sample enough people to have a useful sample?

Guidelines
+ n * p&#772; &ge; 5
+ n(1-p&#772;) &ge; 5

### 2.4 Summary
#### Confidence Interval Comparisons
||Mean(x&#772;)|Proportion(p&#772;)|
|:--|:--|:--|
|n < 30 | x&#772; &plusmn; t<sup>s</sup>&frasl;<sub>&radic;n</sub><br>`x +/- CONFIDENCE.T(alpha, stdev, size)`|`p +/- CONFIDENCE.T(alpha, stdev,size)`|
|n &ge; 30 | x&#772; &plusmn; z<sup>s</sup>&frasl;<sub>&radic;n</sub><br>`x +/- CONFIDENCE.NORM(alpha, stdev, size)`|`p +/- CONFIDENCE.NORM(alpha, stdev,size)`|

