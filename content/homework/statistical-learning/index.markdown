---
title: "HW09: Statistical learning"
date: 2019-05-27T13:30:00-06:00  # Schedule page publish date
publishdate: 2019-04-01

draft: true
type: post
aliases: ["/hw06-stat-learn.html"]

summary: "Implement statistical learning methods for regression and classification."
url_code: "https://github.com/uc-cfss/hw09"
---



# Overview

Due before class June 3rd.

# Fork the `hw09` repository

Go [here](https://github.com/uc-cfss/hw09) to fork the repo for homework 09.

# Part 1: Sexy Joe Biden

![Former Vice President Joe Biden eating an ice cream cone](/img/biden.jpg)

{{< youtube NvbMB_GGR6s >}}

Using statistical learning and data from the [2008 American National Election Studies survey](http://www.electionstudies.org/), evaluate whether or not Leslie Knope's attitudes towards Joe Biden are part of a broader trend within the American public. Specifically, do women display higher feeling thermometer ratings for Joe Biden than men?^[Feeling thermometers are a common metric in survey research used to gauge attitudes or feelings of warmth towards individuals and institutions. They range from 0-100, with 0 indicating extreme coldness and 100 indicating extreme warmth.] `biden.csv` contains a selection of variables from the larger survey that also allow you to test competing factors that may influence attitudes towards Joe Biden.

* `biden` - ranges from 0-100
* `female` - 1 if individual is female, 0 if individual is male
* `pid` - party identification
    * `0` - Democrat
    * `1` - Independent
    * `2` - Republican
* `age` - age of respondent in years
* `educ` - number of years of formal education completed
    * `17` - 17+ years (aka first year of graduate school and up)

1. Estimate a basic (single variable) linear regression model of the relationship between gender and feelings towards Joe Biden. Calculate predicted values, graph the relationship between the two variables using the predicted values, and determine whether there appears to be a significant relationship.
1. Build the best predictive linear regression model of attitudes towards Joe Biden given the variables you have available. In this context, "best" is defined as the model with the lowest MSE. Compare at least three different model formulations (aka different combinations of variables). Use 10-fold cross-validation to avoid a biased estimate of MSE.

# Part 2: Revisiting the Titanic

We've looked a lot at the [Titanic](/notes/logistic-regression/) [data set](/notes/decision-trees/). Now I want you to make your own predictions about who lived and who died.

1. Load the Titanic data from `library(titanic)`. Use the `titanic_train` data frame.
1. Estimate three different logistic regression models with `Survived` as the response variable. You may use any combination of the predictors to estimate these models. **Don't just reuse [the models from the notes](/notes/logistic-regression/#logistic_regression).**
    1. Calculate the leave-one-out-cross-validation error rate for each model. Which model performs the best?
1. Now estimate three random forest models. Generate random forests with 500 trees apiece.
    1. Generate variable importance plots for each random forest model. Which variables seem the most important?
    1. Calculate the out-of-bag error rate for each random forest model. Which performs the best?

# Submit the assignment

Your assignment should be submitted as a set of R scripts, R Markdown documents, data files, figures, etc. Follow instructions on [homework workflow](/faq/homework-guidelines/#homework-workflow). As part of the pull request, you're encouraged to reflect on what was hard/easy, problems you solved, helpful tutorials you read, etc.

# Rubric

Check minus: Cannot get code to run or is poorly documented. No documentation in the `README` file. Severe misinterpretations of the results. Overall a shoddy or incomplete assignment.

Check: Solid effort. Hits all the elements. No clear mistakes. Easy to follow (both the code and the output). Nothing spectacular, either bad or good.

Check plus: Interpretation is clear and in-depth. Accurately interprets the results, with appropriate caveats for what the technique can and cannot do. Code is reproducible. Writes a user-friendly `README` file. Discusses the benefits and drawbacks of a specific method. Compares multiple models fitted to the same underlying dataset.
