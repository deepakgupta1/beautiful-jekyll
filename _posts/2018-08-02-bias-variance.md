---
layout: post
title: Deciphering Bias Vs Variance vis-a-vis Machine Learning Vs Deep Learning
tags: [bias, variance, bias-variance-tradeoff, machine learning, deep learning, overfitting]
---

### Contents
- [**Introduction**](#introduction)
- [**What is Bias and Variance?**](#challenge-description)
- [**A real life example of bias/variance**](#first-look)
- [**Diagnose a model for bias and variance**](#goal-assumptions)
- [**Bias-variance tradeoff in  Machine Learning**](#bug-hunting)
- [**Scenario of bias-variance tradeoff in Deep Learning**](#introduction-to-css-injection)
- [**Key takeaways**](#introduction-to-content-security-policy)
- [**Further reading**](#crafting-exploitaion-strategy)

### Introduction
Bias Vs variance is considered a very basic concept in data science and is easy to understand but tough to keep track in implementations. Bias and variance are like two pans of a weighing balance, you can adjust one at the cost of other. Clear understanding of this concept is crucial for diagnosis of models.
In this blog, I am going to explain all nuances of bias, variance and their tradeoff vis-à-vis Machine learning and Deep learning.

### What is Bias and Variance?
Bias is the measure of how much a model’s predictions differ from the actual values while variance is the measure of the change in a model’s predictions for different training data.

![bulls_eye_diagram](../blogs_resources/bias-vs-variance/bulls_eye_diagram.png)

Consider the figure shown above (taken from Understanding the Bias-Variance Tradeoff), the center of bull’s eye represents the actual outcomes (to be predicted). Every single blue dot represents the cumulative predictions of the model for a set of training data (which changes for every dot). The four combinations of bias and variance could be:

1.	Low bias and low variance: The predictions are not only close to actual values (low bias) but also the predictions don’t differ much in iterations when the training data is changed (low variance), so all dots are gathered around the center close to each other. This is the most desired state.

2.	Low bias and high variance: The predictions are close to actual values (low bias) but differ greatly in iterations of training with varied data (high variance), so all dots are close to center but far from each other.

3.	High bias and low variance: The predictions are far from actual values (high bias) but don’t differ in iterations of training with varied data (low variance), so all dots are far from center but are close to each other.

4.	High bias and high variance: The predictions are not only far from actual values (high bias) but also far from each other (high variance), so all dots are far from center as well as each other. This is the worst of both worlds.

### A Real Life Example of Bias-Variance
Let’s understand this with a simple example. Consider that you are getting married and lot of guests are invited (more than a 1000, yeah, an Indian wedding). And because you want to give your guests best dining experience you decide to analyze their food preferences: Vegetarian/Non- vegetarian. 

You collect data of 50 guests (these are your close friends). The distribution you got is:

| Vegetarian | Non Vegetarian | Non Respondent | Total | 
| ---------- |:--------------:| --------------:| -----:|
| 18         | 25             | 7              |   50  |
 
Now you make a machine learning model based on different characteristics of these 50 friends of yours and their preference. These characteristics may include gender, age (most of them are quite young), living region (nearby you), religion and so on. 
This model is suffering from both high variance and high bias. This is how:

High bias: By just selecting your friends, you limit model’s understanding to only a certain class of people (young, nearby living, because they are your friends) and so the predictions on new data will be very wrong thereby increasing bias. 

High variance: Small sample size (just 50) is the major source of high variance. If the sample size is increased, then the result would be more consistent. In the bulls- eye diagram, the scatter would clump together if sample size is increased.

### Diagnose a Model for Bias and Variance
To diagnose a model for bias and variance, we need to understand its relationship with underfitting and overfitting of the model.
Underfitting: The model’s performance is poor i.e. predicted values are far from actual values which implies high bias.
Overfitting: The complexity of model has increased to a level that the model is tightly coupled with the training data itself and is not general enough which implies high variance.
To identify bias and variance in a model, a most popular technique used in both academia and industry is cross validating a model. In cross validation a small part of the train data set is separated out as cross validation set and the trained model is then tested on this cross-validation set.


