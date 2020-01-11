# The Presumptuous P-value

When conducting research, many people want to know if all of the hard work they put in and data that they collected means anything. Thus, in order to quantify the statistical significance of a researcher's findings, it has become common practice, although recently a more controversial one, to determine the reliability of an experiment by using a calculated probability known as the *p-value*. In order to demonstrate this concept, let's consider an example;

Imagine you are a very conscientious nutritionist and want to know whether your female clients are on average eating more or less servings of fruits and vegetables (fruitables) per day than the average female citizen. Luckily, the government has already collected some data from a large sample of 1.3 million women and found that the average amount of fruitables eaten per day was 4.90, with a standard deviation of 0.1 [StatCan, 2002](https://www150.statcan.gc.ca/n1/en/pub/82-003-x/2001003/article/6103-eng.pdf?st=YqoR0ZlM). 25 of your 40 clients on average eat 6.08 servings per day. Let’s call this value your test statistic, as it is a statistic that you would like to test or compare. It doesn’t do much good to just eyeball these two averages and say, “Well obviously 6.08 is much higher than 4.90, so you are doing a great job, you deserve a raise”. In order to conduct an unbiased scientific test to see how unusual your results are, most statisticians will tell you to find out how unusual your results are, assuming that the average or null hypothesis is true using something called a hypothesis test and a p-value. Before I explain how to conduct a hypothesis test with this data and what a p-value is, and why you might want to use it, I will define a few important terms:

- Definition of *null hypothesis*:  A hypothesis which states that there is no significant difference between specified populations, and any observed difference is due to sampling or experimental error. This statement is usually more specific and uninteresting than the alternate hypothesis, as it is expected under normal circumstances. Usually researchers are trying to disprove this hypothesis, as it is interesting to find support for something that is not yet known or expected.
Eg. The sun rises in the east.

- Conversely, an *Alternate hypothesis* is not specific and is essentially a statement that describes the null hypothesis not happening, and is usually more interesting than the null hypothesis. The alternate hypothesis can be either *1-tailed* or *2-tailed* depending on if there are possible parameter values on one or both sides of the value specified by the null hypothesis respectively.
Eg. The sun does not rise in the east.

In this case, your null hypothesis is that your clients are eating on average 4.9 servings of fruitables per day. Your alternate hypothesis would be that the population parameter for your 40 clients is not 4.9 servings of fruitables per day. Since it is possible for your clients to be eating more or less than the average, we can say that this is 2-tailed test.

Now the tricky part is finding out what the null distribution is, which you need in order to carry out a hypothesis test. In order to do this, you can create a null distribution for your test statistic, by simulating a bunch of scenarios (how about 80!) with the same sample size of 25 people, and a mean of 4.9, and standard deviation of 0.1 (as this is what was found in the population study). Then record the mean serving of fruitables consumed in each trial and display them with a probability distribution. Here is what those sample means from your simulated 80 trials might look like:

![fruitables](https://github.com/heathervant/What-is-a-p-value-/blob/master/Fruitables.png)

Now, the beauty of the p-value is that it can tell you what the likelihood is of obtaining a new result, assuming that what you have observed previously in the population is true. The p value is a conditional probability and in true probability form, cannot be negative or larger than 1. The lower the p value - the more evidence we have against the null hypothesis and therefore the more likely we can reject it. This means our test is more reliable and has a stronger argument to support our alternate hypothesis.

In order to calculate your p-value for this experiment, you would take your test statistic value of 6.08 and see if it is as weird or weirder than getting the average result of 4.9 by using this normal distribution. Since it is a 2-tailed test, this means finding the area under the normal probability distribution on either end of the curve that corresponds to being equal to or greater than 6.08 as well as less than or equal to -6.08. A computer can find an exact p-vale, but usually we can just look up the rounded p-value in a table that mathemeticians have kindly generated for us. These calculations that takes into account the degrees of freedom, which refers to the number of values involved in the calculations that have the freedom to vary or more loosely- number of variables. To re-iterate, this p-value tells us the probability of obtaining our result under the null hypothesis.

Depending on the significance level that the scientific community deems acceptable, we can determine whether to reject or fail to reject the null hypothesis. The most commonly used significance threshold- also known as the alpha-value- is 0.05. So if our p-value is less than the significance threshold of 0.05, this means that the probability of obtaining this test statistic assuming the null hypothesis is true is less than 5%. Think of it as obtaining a result that is really weird, and would only occur less than 5% of the time if the null were true. If our p-value is greater than alpha, no conclusions can be made regarding our question and we therefore fail to reject the null hypothesis, or in other words, we support the null hypothesis.

In this example, our p-value is 0.0001, which is less than alpha. Thus, we can reject our null hypothesis and support the alternate hypothesis. Your clients do eat more fruit than the national average. You do deserve a raise and recognition!

![puppies](https://gph.is/1Q3Ksr2)


## Common Misconception of the p-value
The p-value tells you about the likelihood of obtaining these results assuming that the average or expected value is correct or true. Thus, it tells you about how good your test is at finding an unexpected result. It does not however tell you anything about whether or not your sample is truly different than the what is expected due to chance, given the test statistic. 
 

## History of the p-value
The p-value was originally invented to determine whether something was worth investigating further. The p-value was later popularized by  Ronald Fisher, who devised an approach called “significance testing” which he used to make inferences based on the evidence in the data. Eight years later, two other statisticians named Neyman and Pearson invented “hypothesis testing”, which assumed that no experiment could provide evidence about any particular hypothesis and instead focused on minimising  wrong conclusions. These two different concepts can sometimes be confused, and is worth further reading.

## Ethical use of p-values
It is important to set the significance level before analyzing your results for ethical reasons. Otherwise, you may be tempted to change the significance level to be larger than your p-value to make your findings seem more interesting. Or worse, researchers may manipulate the data, which might involve leaving out some data points or asking a slightly different question, to obtain a significant result. This is known as p-hacking, and is frowned upon, as it decreases the integrity and reliability of findings. 

For further reading, I suggest this [article](http://theconversation.com/give-p-a-chance-significance-testing-is-misunderstood-20207) as it has many interesting links.

**References**
Dorey, F. (2010). In Brief: The P Value: What it is and What Does it Tell you? Clinical Orthopaedic and Related Research. 468(8): 2297–2298. doi: 10.1007/s11999-010-1402-9
