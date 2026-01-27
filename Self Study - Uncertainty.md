# Probability
Probability asks: **Given what I know, how confident can I be about something I don't know**. 

Examples: 
1. Given that I hear thunder, how like is it that there is rain.
2. Given an email with certain words. How likely is it spam. 

# Bayesian Probability
- Bayesian probability updates our beliefs based on data we do know. This is an example of learning. 
	1. You start with a belief
	2. You observe available data
	3. You update your belief

## Bayes' Rule
Bayes rule is the following formula 

$$
P(Hypothesis | Data) = \frac{P(Data | Hypothesis) * P(Hypothesis)}{P(Data)}
$$
Where 
P(Hypothesis|Data) -> The probability of the hypothesis given data.
P(Data|Hypothesis) -> How likely the data is if the hypothesis were true. 
P(Hypothesis) -> Probability of just the hypothesis 
P(Data) -> Probability of the Data being the true

### Example:
P(rain | clouds) : Probability of rain given that there are clouds.
P(clouds | rain): Probability of clouds, given that there is rain. 

### Full Example:
Given a 1% chance of a disease, and a test with 99% positive accuracy, and 5% false positive rate
P(Disease) = 0.01
P(+ | Disease) = 0.99
P(+ | NoDisease) = 0.05

What is P(Disease | +)

First we must fine P(+), which are cases were is where you have the disease (you have diesase, test positive) + (you dont have diease and test positive)
$$
P(+) = (0.99 * 0.01) + (0.05 * 0.99) = 0.0594
$$
Then we can calculate the probability of having the disease, given the positive test result. 
$$
P(Diesase | +) = \frac{P(+ | Disease) * P(Disease)}{P(+)} = \frac{0.99 * 0.01}{0.0594} = 0.1667
$$

Therefore, there is only a ~16.7\% chance of having the disease. 