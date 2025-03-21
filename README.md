#AB Testing - Introduction

## Introduction
In this section, you'll get to develop your skills regarding AB testing. Before diving in, take a minute to note some key points which you should keep in mind when completing the various labs and conducting your own hypothesis tests in practice.
Experimental Design
You've seen that a lot goes into the proper design of statistical tests. You've learned about Goodheart's law as well as the multiple comparisons problem. Additionally, you've also seen that a p-value by itself is prone to misinterpretation if not presented with other relevant design parameters such as effect size, sample size, and   . With that, here are three overarching considerations to keep in mind.
Well Formulated Questions
A well-formulated question is essential to a good statistical experiment. This includes careful thought of unintended consequences, as you saw in the discussion of Goodheart's law. Additionally, the question should also be specific and measurable.
Choosing Appropriate Parameters
It cannot be stressed enough how important the relationship between   , power, sample size and effect size is. While larger sample sizes provide more powerful tests, one should also realize that tiny effects can produce significant p-values with large samples. While this may be interesting, such small practical differences might have little to no applicable value. Furthermore, avoiding pitfalls such as the multiple comparisons problem is also important. Recall that if you perform multiple t-tests, The probability of encountering a type I error will continue to increase with additional tests. (Each test will still have the corresponding alpha value set, but collectively, the chance that a false positive type I error exists in your conclusions increases.)
Preprocessing, Data Anomalies and Outliers
On the other end of problem formulation is formatting the data to actually answer said question. You'll encounter this most explicitly in the final lab of this section. There, you'll have to transform your data into an appropriate format before conducting the statistical test. Furthermore, it's important to note how idiosyncrasies in your data can impact results. For example, monumental outliers can drastically impact the outcome of statistical tests. Whether or not to remove these data points can be a source of contention and will vary upon the circumstance. Similarly, it should go without saying that erroneous data or faulty data will clearly degrade statistical tests. All in all, it's always important to get familiar with the structure of the data and the context of the question being asked before diving into the statistics themselves.
## Summary
Time to have at it! Dive in and start practicing some hypothesis testing!

## A/B Testing
  
## Introduction
You've now seen all of the statistical techniques and background to design and conduct your own A/B tests in practice! To do this, you'll go through the process of stating the null hypothesis and the alternative hypothesis which will include some test statistic for comparison. For example, you might compare the average purchase price between customers on two different versions of your online store, or a pharmaceutical researcher might compare the blood pressure of patients before and after taking a prescription. You've also seen that good test design requires multiple decisions. Recall both the multiple comparisons problem and Goodheart's law: you can't effectively measure everything (without increasing the risk of mistakes), and incentivizing measurements can lead to unforeseen consequences. With that, this section will give you a chance to put your new statistical techniques into practical applications.
## Objectives
You will be able to:
* List the steps required to design, structure, and run an A/B test
* Choosing a Metric
Any hypothesis testing will start with a given scenario. This will determine everything from what metrics are deemed important to realistically obtainable sample sizes. Goodheart's law can also be an important consideration when performing ongoing tests in attempts to optimize performance metrics.
## Defining the Null Hypothesis:  
Once an appropriate metric has been selected, it's time to formally define the experiment with a null hypothesis. Typically, the null hypothesis is the claim that a researcher is hoping to refute. For example, a medical researcher might hope to show that a new drug is more effective than a previous treatment option. A common practice is then to define the null hypothesis as the contrary: there is no difference between the two drugs. The researcher hopes to refute the null hypothesis thereby proving their claim by contradiction.
You might start with something like "   is more effective than   ".
While this is a good start, proper formulation of the null hypothesis should ensure that it is written with a quantitative measurement. Perhaps the drugs are for high blood pressure and so the statement becomes, "   at   lowers blood pressure more than   at   ".
Formulating the null-hypothesis like this is apt to lead you into conducting a paired t-test for the mean blood pressure of two groups: one representing   , and another representing   .
Alternatively, if one of these two medications were more heavily researched, one might wish to compare the effectiveness of the new medication with a predetermined metric such as the average drop in blood pressure from medication. This would lead to a 1-sample t-test, as opposed to a two-sample t-test.
### Investigating   , power, effect size, and sample size
Finally, one must formulate the various surrounding parameters required to conduct the test. You've seen that there is an intimate relationship between   , power, sample size, and effect size. With that, questions such as "How costly is sample size?" are instrumental in experiment design. For example, in an online scenario, it might be quite easy to conduct experiments at scale. On the other hand, in medical research, larger sample sizes are apt to be extremely costly. Investigating the relationships between   , power, effect size, and sample size is important for all experiments, and a suitable combination will depend on these contextual factors regarding implementation.
Summary
When researching, you are often presented with two choices for stating a question. One is to estimate a parameter in question, such as the procedures previously examined for estimating the mean of a population. Alternatively, you may wish to test the validity of a claim—whether you can refute that claim, or whether you should withhold judgment. In practice, it is up to the practitioner to determine the appropriate alpha, beta, and sample size that is determined to be both satisfactory confidence and a viable sample size to attain. In the upcoming labs, you'll get to practice this


# A/B Testing - Lab

## Introduction

In this lab, you'll go through the process of designing an experiment.

## Objectives
You will be able to:

* Design, structure, and run an A/B test


## The Scenario

You've been tasked with designing an experiment to test whether a new email template will be more effective for your company's marketing team. The current template has a 5% response rate (with standard deviation .0475), which has outperformed numerous other templates in the past. The company is excited to test the new design that was developed internally but nervous about losing sales if it is not to work out. As a result, they are looking to determine how many individuals they will need to serve the new email template in order to detect a 1% performance increase.


## Step 1: State the Null Hypothesis, $H_0$

State your null hypothesis here (be sure to make it quantitative as before)


```python
# H_0 = Your null hypothesis
```

## Step 2: State the Alternative Hypothesis, $H_1$

State your alternative hypothesis here (be sure to make it quantitative as before)


```python
# H_1 = Your alternative hypothesis
```

## Step 3: Calculate n for standard alpha and power thresholds

Now define what $\alpha$ and $\beta$ you believe might be appropriate for this scenario.
To start, arbitrarily set $\alpha$ to 0.05. From this, calculate the required sample size to detect a .01 response rate difference at a power of .8.

> Note: Be sure to calculate a normalized effect size using Cohen's d from the raw response rate difference.


```python
# Calculate the required sample size
```

## Step 4: Plot Power Curves for Alternative Experiment Formulations

While you now know how many observations you need in order to run a t-test for the given formulation above, it is worth exploring what sample sizes would be required for alternative test formulations. For example, how much does the required sample size increase if you put the more stringent criteria of $\alpha=.01$? Or what is the sample size required to detect a .03 response rate difference at the same $\alpha$ and power thresholds? To investigate this, plot power vs sample size curves for alpha values of .01, .05 and .1 along with varying response rate differences of .005, .01, .02 and .03.


```python
#Your code; plot power curves for the various alpha and effect size combinations
```

## Step 5: Propose a Final Experimental Design

Finally, now that you've explored some of the various sample sizes required for statistical tests of varying power, effect size and type I errors, propose an experimental design to pitch to your boss and some of the accompanying advantages or disadvantages with it.

### Your answer here


```python

```

## Summary

In this lab, you practiced designing an initial experiment and then refined the parameters of the experiment based on an initial sample to determine feasibility.
