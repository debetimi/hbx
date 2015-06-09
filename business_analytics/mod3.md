# Module 3 -  Hypothesis Testing

## 3.1 - Introduction 

### 3.1.1 - Amazon's Use of Hypothesis Testing

Methods for Collecting Samples 
 1. Survey - Ask questions and record self reported responses from random sample of populatiojn.jlko
 2. Observational Study - Observe and Collect Data about sample as they occur naturally without intervention
 3. Experiment - Divid sample into two groupts.  In one group, "treatment" group, manipulate a variable and compare responses to control group.

 
Amazon uses _A/B Testing_ which is commonly used in software testing. Amazon will change the way the site looks or add new features, and send a random sample of visitors to this modified page and then collect metrics and analyze the data.


## 3.2 - Designing and Performing Hypothesis Tests

### 3.2.1 Developing Hypotheses

**Null Hypothesis (H<sub>0</sub>)** - Statement about a topic of interest based on historical information or conventional wisdom.  We start a hypothesis test by assuming the null hypothesis is true an then test to see if we can nullify it.

**Alternate Hypthesis (H<sub>a</sub>) - Opposite of the Null Hypothesis thisi s the claim we are trying to substantiate. If our data allows us to nullify the null hypothesis, we substantiate the alternative hypothesis.

Hypothesis Test has two possible outcomes.  We either reject the null hypothesis, or we fail to reject it because we have inconclusive evidence.

 + Example Criminal Law: H<sub>0</sub> = Accused is Innocent. H<sub>a</sub> the accused is guilty.  The possible outcomes from the trial are guilty or not guilty.  Meaning we can reject the null hypothesis with guilty, or re can fail to reject it with not guilty.  But we cannot confirm it, meaning we can't say the defendant is innocent.

### 3.2.2 Constructing a Range of Likely Sample Means

**Example: Movie Goer Satisfaction**

Lets say our previous statisfaction was 6.7 and our null hypthesis is satisfaction hasn't changed. And now we do a randomize sample and get a new satisfaction of 7.3 and standard deviation of 2.8.  Has the satisfaction really changed?  Or is it the same and we just happened to draw a sample with abnormally high satisfaction?

To answer this question we have to construction a  *Range of Likely Sample Means*.  

**Range of Likely Sample Means** - This is a range we expect n% of samples means to fall between.  It is centered at the  _Null Hypothesis_ and follows a normal distribution since we know that the distribution of sample means is normal via the _Central Limit Theorem_.


Rejection Region - All values outside the n% region are rejected. N is defined by the creator of experiment.
Using the numbers in our example, and the _confidence interval__ functions from module 2 we can determine that if the  null hypothsis is true, and the average satisication is 6.7 then there is 95% chance that satisfaction falls between 6.3 to 7.1.  Since 7.3 doens't fall into that range we reject the null hypothesis.


### 3.2.3 Using P-values

**P-Value** - Measure of likelihood. This is the likelihood of choosing a value a value given that null hypothesis is correct.
 + Suppose that the value falls in the rejection region using 95% interval. Then we know that the p-value is less than 5 percent.
 + Thus when we take sample we reject it the null hypothesis if the p-value is less than 5%. 
 + The smaller the _p-value_ the stronger the evidence is against the null hypothesis.

**Significance Level &alpha;** - The level at which we reject a null hypthosis.
 + Significance Level = 1 - Confidence Level

To find P value use `T.TEST(array1, aray2, tails, type)`
+ array1 is a set of numerical values or cell references. We will place our sample data in this range.
+ array2 is a set of numerical values or cell references. We have only one set of data, so we will use the historical mean, 6.7, as the second data set. To do this, we create a column with each entry equal to 6.7.
+ tails is the number of tails for the distribution. It can be either 1 or 2. We will learn more about what this means later in the module. Since our alternative hypothesis is that the mean has changed and therefore can be either lower or higher than the historical mean, we will be using a two-tailed, or two-sided hypothesis test.
+ type can be 1, 2, or 3. Type 1 is a paired test and is used when the same group is tested twice to provide paired “before and after” data for each member of the group. Type 2 is an unpaired test in which the samples are assumed to have equal variances. Type 3 is an unpaired test in which the samples are assumed to have unequal variances. The variances of the two columns are clearly different in our case, so we use type 3. There are ways to test whether variances are equal, but when in doubt, use type 3.


### 3.2.4 Type 1 and Type 2 Errors

||Null Hypothesis Is True| Null Hypothesis is False |
|:---|:----:|:-----:|
|Reject the Null Hypothesis|Type 1 Error<br/>1 - Confidence Interval% chance<br/>False Positive| Correct Conclusion |
|Do Not Reject the Null Hypothesis | Correct Conclusion<br/>Confidence Interval% chance | Type II Error<br/>False Negative | 

You can reduce Type 1 errors be increasing the confidence interval however this will increase Type 2 errors.


### 3.2.5 One Sided Hypothesis Test

If you have compelling evidence that change has occurred in a specific direction, then you can perform a test only only in that direction.  This is known as a one sided hypothesis test.

Note: When calculating confidence intervals for one sided hypthesis remember that the confidenc.norm function is double sided, so you need to adjust. For example 95% Confidence interval on 1 sided is an &alpha; value of 0.1 and not 0.5 this is because we want 5% rejection range on the 1 side.

To find P value use `T.TEST(array1, aray2, tails, type)`
 + In one sided make sure that tails is 1.

## 3.3 Improving the Customer Experience

### 3.3.1 The Shopping Cart A/B Test

They changed the shopping cart logo from static to show the number of items in the cart.  The results for the total amount purchased and the total number of units purchased showed significant results, so they went ahead and changed it.

### 3.3.2 The Arrow A/B Test

Control: Semi-Circle behind Arrow.  Treatment: No Semi Circle.

### 3.3.3 The Magazine A/B Test

Control: Books. Treatment: Books & Magazines.
Results: Slightly negative affect on Ordered Product Sales, but not meaningful.  Meaningful worsening on Total U nits Ordered (p = 0.0448)

Challenges of A/B Testing
 + Effects are very small
 + If you do too many tests at once you might miss the affects the individual tests.
  + Amazon is careful to isolate the changes.
 + Have to go back and retest conclusions to make sure they persist.
