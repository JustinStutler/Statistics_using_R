<img src="portrait.jpg" 
  width="50%"
  height="50%"/>
# Justin Stutler
### Sophomore USF Information Science - Data Science and Analytics
### Jstutler@usf.edu

### About me
### Hello all. I am Justin Stutler. I previoiusly studied Computer Science and played esports at Kennesaw State University. I have worked some in web development and enjoyed the challenges, but I am more interested in working in the Data Science field. After the creation of AlphaGo and AlphaZero, how could I not be interested in pursuing data?
### Outside of school, I enjoy yoga, cooking, board games, video games, anime, documentaries, learning, and meeting new people.
&nbsp;
&nbsp;
### First R Studio Assignment LIS 4372
``` 
1 assignment = c(6,18,14,22,27,17,22,20,22)
2 myMean = function(assignment) {
3 return(sum(assignment)/length(assignment))
4 }
5 myMean(assignment)
```
### So, what happens in the code above?
```
1: we created a container "assignment" that holds the data values of 6,18,14,22,27,17,22,20,22
2-4: we created a function "myMean" that returns the mean of a given container
5: we called "myMean" with a parameter of (assignment) which returned 18.66667 as the mean of assignment
```
&nbsp;
&nbsp;
### Module 3 R Studio Assignment LIS 4372
```
s1 = c(10,2,3,2,4,2,5)
s2 = c(20,12,13,12,14,12,15)

# for each set
# compute mean, median, mode under Central Tendency
# mean
s1mean = mean(s1)
s2mean = mean(s2)
# median
s1median = median(s1)
s2median = median(s2)
# create mode function
getMode = function(data) {
  uniqv = unique(data)
  uniqv[which.max(tabulate(match(data, uniqv)))]
}
# mode
s1mode = getMode(s1)
s2mode = getMode(s2)
# compute range, interquartile, variance, standard deviation under Variation
# range
s1range = range(s1)
s2range = range(s2)
# interquartile
s1IQR = quantile(s1)
s2IQR = quantile(s2)
# variance
s1variance = var(s1)
s2variance = var(s2)
# standard deviation under variation
s1SD = sd(s1)
s2SD = sd(s2)
# results
summary(s1)
summary(s2)
```
<img src="module3DataSummary.png" 
  width="50%"
  height="50%"/>
### Comparing Datasets s1 and s2 
### The values in the dataset s2 are equivalent to the values of dataset s1 + 10. The interquartile range, mean, median, mode, and range of s2 are equivalent to the values in s1 + 10. The variance of s1 and s2 is the same at 8.3 repeating. The standard deviation of s1 and s2 is the same at ~2.887. The variance and standard deviation of the datasets are the same because the values deviated from the mean the same amount.

&nbsp;
&nbsp;

### Module 4 Assignment
&nbsp;
<img src="question_a.JPG"/>
&nbsp;
````
A. 
a1. P(A) = 10/90 + 20/90 = 30/90 = 1/3
a2. P(B) = 10/90 + 20/90 = 30/90 = 1/3
a3. P(A | B) = P(A + B) = P(A) + P(B) - P(A n B)
P(A | B) = 1/3 + 1/3 - 1/9 = 5/9
a4. P(A | B) = P(A) + P(B)?
P(A | B) = 5/9
P(A) + P(B) = 1/3 + 1/3 = 2/3
5/9 != 2/3
P(A | B) != P(A) + P(B)? no
````
&nbsp;
<img src="question_b.JPG"/>
&nbsp;
````
B. 
b1. The answer of 11% is true.
b2. We know the answer is true. Bayes’ Theorum allows us to evaluate the probability of the weatherman’s successful prediction of rain. 
This value, 11.11%, tells us that it will not rain more often than not when the weatherman predicts rain. 
Therefore, there is about a 89% chance it will not rain on Jane’s wedding day tomorrow.
````
&nbsp;
<img src="question_c.JPG"/>
&nbsp;
````
C.
* using RStudio we get
C1. dbinom(10, 10, 0.2) = 1.024e-07
The probability of 10 successes in a row given a probability of success of 0.2 (20%) is 1.024e-07.
````

&nbsp;
&nbsp;
## Module 5 Assignment : P-val and Correlation Analysis
### First Question: 
### The director of manufacturing at a cookies needs to determine whether a new machine is production a particular type of cookies according to the manufacturer's specifications, which indicate that cookies should have a mean of 70 and standard deviation of 3.5 pounds. A sample pf 49 of cookies reveals a sample mean breaking strength of 69.1 pounds.
### A. State the null and alternative hypothesis _______
```
Null Hypothesis (H_o) : u ≥ 70
The cookies have a breaking strength of 70 or greater.
Alternate Hypothesis (H_a) : u < 70
The cookies have a breaking strength of less than 70.
```
### B. Is there evidence that the machine is not meeting the manufacturer's specifications for average strength? Use a 0.05 level of significance _______ 
### C. Compute the p value and interpret its meaning _______
```
1. Specify the level of significance
    level of significance (a) = 0.05
2. Compute the Z-value
    z = (mean - u)/(sd / sqrt(n))
    mean = 70
    u = 69.1
    sd = 3.5
    n = 49
    z = (70 - 69.1) / (3.5 / sqrt(49)) = 1.8
3. Compute p-val
    for z = 1.8, cumulative probability = 0.964070
    p-val = 1 - cumulative probability = 1 - 0.964070 = 0.03593
4. Determine whether to reject H_o    
    Because the p-value of 0.03593 < 0.05, there is sufficient statistical evidence to infer the cookies do not meet the manufacturer’s specification of an average breaking strength of 70 lbs.
```
### D. What would be your answer in (B) if the standard deviation were specified as 1.75 pounds?______
```
if sd = 1.75, z = ?
z = (70 - 69.1) / (1.75 / sqrt(49)) = 3.6
cumulative probability = 0.99984
p-val = 1 - 0.99984 = 0.00016
Because the p-value of 0.00016 < 0.01, there is a significant amount of statistical evidence to infer the cookies do not meet the manufacturer’s specification of an average breaking strength of 70.
```
### E. What would be your answer in (B) if the sample mean were 69 pounds and the standard deviation is 3.5 pounds? ______
```
if mean = 69, sd = 3.5, z = ?
z = (70 - 69) / (3.5 / sqrt(49)) = 2
cumulative probability = 0.97725
p-val = 1 - 0.97725 = 0.02275
Because the p-value of 0.02275 > 0.05, there is sufficient statistical evidence to infer the cookies do not meet the manufacturer’s specification of an average breaking strength of 70.
```
&nbsp;
### Second Question:
### If x̅ = 85, σ = standard deviation = 8, and n=64, set up 95% confidence interval estimate of the population mean μ. 
```
given : mean = 85, sd = 8, n=64
set up a 95% confidence interval estimate of the population mean u
z = 1.96 for 95% confidence
Confidence Interval Formula
mean +- z(sd / sqrt(n))
85 + 1.96(8/sqrt(64)) = 86.96
85 - 1.96(8/sqrt(64)) = 83.04
With 95% confidence the population mean is between 83.04 and 86.96, based on 64 samples.
```

&nbsp;

### Third Question
### using the following dataset

<img src="girlBoyData.JPG"/>

### a. Calculate the correlation coefficient for this data set _____
```
The correlation coefficient comparing the total values for girls and boys is 0.9999681; This indicates a strong positive correlation of 0.99.
More Correlations can be found below.
```

<img src="girlBoyCorr.JPG"/>

### b. Pearson correlation coefficient _____

```
The Pearson correlation coefficient comparing the total values for girls and boys is 0.9999681; this indicates a strong positive correlation of 0.99.
More Correlations can be found below.
```

<img src="girlBoyPearsonCorr.JPG"/>

### c. Create plot of the correlation
<img src="corrgramGirlsBoys"/>

### Completed in R below

```
# Module 5 Assignment
# Correlation Analysis
setwd("C:/Users/justi/Desktop/r")

# x = girls, y = boys
# vars = goals, grades, popular, time

# create data
# create girls
goals = c(4, 5, 6)
grades = c(49, 50, 69)
popular = c(24, 36, 38)
timeSpent = c(19, 22, 28)
total = c(92, 108, 135)
girls = data.frame(goals, grades, popular, timeSpent, total)
girls

# create boys
# goals is the same
grades = c(46.1, 54.2, 67.7)
popular = c(26.9, 31.6, 39.5)
timeSpent = c(18.9, 22.2, 27.8)
total = c(95.9, 113, 141)
boys = data.frame(goals, grades, popular, timeSpent, total)
boys

cor(girls, boys)

data = data.frame(girls, boys)
data

# correlation
cor(data, method="pearson")
cor(data, method="spearman")
# plot
corrgram(data)
```

## Module 6 Assignment
### A
```
// Module 6 Assignment
// Justin Stutler

// A
// consider a population: 8,14,16,10,11
p = c(8,14,16,10,11)
// compute mean and standard deviation
pmean = mean(p)
pmean

psd = sd(p)
psd

// select a random sample of size 2
sample = c(16, 11)

// compute mean and standard deviation for sample
smean = mean(sample)
smean

ssd = sd(sample)
ssd

// compare sample mean and sd to population
smean
pmean
ssd
psd


// smean of 13.5 is larger than pmean of 11.8
// ssd of 3.536 is larger than psd of 3.194
```
### B
```
// B
// n = 100, p =0.95
pn = 0.95 * 100
pn
// pn = 95 >= 10
qn = 0.05 * 100
// qn = 5 ! >= 10
// therefore not normal distribution
// 10 = 0.05n
n = 10 / 0.05
n
// smallest value is n = 200
```
### C
### explain how rbinorm is probably more suited for coin flip simulation than sample.
```
rbinorm is suited for something with 2 mutually exclusive outcomes with consistent probability such as flipping a coin. The 2 mutually exclusive outcomes are landing heads or tails with each of the options having a consistent probability of 0.5.

Sampling can be used with replacement or without. Sampling without replacement would not work in the case of flipping a coin. Sampling with replacement would work if the sample contained an equal amount of heads and tails options, but the concept of flipping a single object with a binary outcome just comes more naturally froma binomial distribution.
```

## Module 7 Assignment
### R Code
```
// Module 7 Assignment
// Regression
// Justin Stutler

// 1.1 Define the relationship between the predictor and response variable
// Predictor: X
// Response: y
// Describe x by y

d.data = data.frame(
 x = c(16, 17, 13, 18, 12, 14, 19, 11, 11, 10),
 y = c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
)
d.data

// 1.2 calculate the coefficients
d.regression = lm(x ~ y, data = d.data)
d.regression

// 2
// create data
visit.data = data.frame(
  discharge = c(3.600, 1.800, 3.333, 2.283, 4.533, 2.883),
  waiting = c(79, 54, 74, 62, 85, 55)
)
visit.data

// 2.1
// Predictor: discharge
// Response: waiting
// Describe discharge by waiting
visit.regression = lm(discharge ~ waiting, data = visit.data)
visit.regression

// 2.2 extract coefficients
visit.coeffs = coefficients(visit.regression)
visit.coeffs

// 2.3 fit discharge duration
wait = 80
duration = visit.coeffs[1] + visit.coeffs[2]*wait
duration

// 3
// load mtcars data set
car.data = mtcars[,c("mpg","disp","hp","wt")]
print(head(car.data))

// 3.1 Examine the relationship Multi Regression Model as stated above and its Coefficients using 4 different variables from mtcars (mpg, disp, hp and wt). 
// what does the multi regression model and coefficients tells about the data? 
car.regression = lm(formula = mpg ~ disp + hp + wt, data = car.data)
car.regression
// (Intercept) gives the y intercept
// disp, hp, wt display the change in these variables per 1 mpg change 

// 4
// required library
library(ISwR)
// 4.1 According to the fitted model, what is the predicted metabolic rate for a body weight of 70 kg? 
plot(metabolic.rate~body.weight,data=rmr)

r = lm(metabolic.rate ~ body.weight, data = rmr)
r
coeffs = coefficients(r)
coeffs
body_weight = 70
dur = coeffs[1] + coeffs[2]*body_weight
dur

// Based on the simple linear regression model, if the body weight is 70 kg, we expect the metabolic rate to be 1305.394
```

### R Studio Console

<img src="assignment7.1.JPG"/>
<img src="assignment7.2.JPG"/>
<img src="assignment7.3.JPG"/>
<img src="assignment7.4.JPG"/>


## Assignment 8 : ANOVA
### R Studio Code
<img src="assignment8.0.JPG"/>
### R Studio Console
<img src="assignment8.1.JPG"/>
<img src="assignment8.2.JPG"/>
<img src="assignment8.3.JPG"/>

## Assignment 9
### R Studio Code
<img src="assignment9.0.JPG"/>
### R Studio Console
<img src="assignment9.1.JPG"/>
<img src="assignment9.2.JPG"/>
<img src="assignment9.3.JPG"/>
<img src="assignment9.4.JPG"/>
<img src="assignment9.5.JPG"/>
<img src="assignment9.6.JPG"/>
<img src="assignment9.7.JPG"/>
<img src="assignment9.8.JPG"/>

## Assignment 10
### R Studio Code
<img src="assignment10_code.JPG"/>

### R Studio Console
<img src="assignment10.1.jpg"/>
<img src="assignment10.2.jpg"/>
<img src="assignment10.3.JPG"/>


## Assignment 11
### R Studio Code
<img src="assignment11.code.0.JPG"/>
<img src="assignment11.code.1.JPG"/>

### R Studio Console
<img src="assignment11.0.JPG"/>
<img src="assignment11.1.JPG"/>
<img src="assignment11.2.JPG"/>
<img src="assignment11.3.JPG"/>
<img src="assignment11.4.JPG"/>
<img src="assignment11.5.JPG"/>
<img src="assignment11.6.JPG"/>
<img src="assignment11.7.JPG"/>

## Assignment 12
### R Studio Code
<img src="m12_code.JPG"/>

### R Studio Console
<img src="m12_console1.JPG"/>
<img src="m12_console2.JPG"/>
<img src="m12_plot.JPG"/>
<img src="m12_console3.JPG"/>


