---
layout: post
title: Deciphering Bias Vs Variance vis-a-vis Machine Learning Vs Deep Learning
tags: [bias, variance, bias-variance-tradeoff, machine learning, deep learning, overfitting]
---

### Contents
- [**What is Bias and Variance?**](#challenge-description)
- [**A real life example of bias/variance**](#first-look)
- [**Diagnose a model for bias and variance**](#goal-assumptions)
- [**Bias-variance tradeoff in  Machine Learning**](#bug-hunting)
- [**Scenario of bias-variance tradeoff in Deep Learning**](#introduction-to-css-injection)
- [**Key takeaways**](#introduction-to-content-security-policy)
- [**Further reading**](#crafting-exploitaion-strategy)

Bias Vs variance is considered a very basic concept in data science and is easy to understand but tough to keep track in implementations. Bias and variance are like two pans of a weighing balance, you can adjust one at the cost of other. Clear understanding of this concept is crucial for diagnosis of models.
In this blog, I am going to explain all nuances of bias, variance and their tradeoff vis-à-vis Machine learning and Deep learning.

### What is Bias and Variance?
Bias is the measure of how much a model’s predictions differ from the actual values while variance is the measure of the change in a model’s predictions for different training data.

![bulls_eye_diagram](../blogs_resources/bias-vs-variance/bulls_eye_diagram.png)

Consider the figure shown above (taken from Understanding the Bias-Variance Tradeoff), the center of bull’s eye represents the actual outcomes (to be predicted). Every single blue dot represents the cumulative predictions of the model for a set of training data (which changes for every dot). The four combinations of bias and variance could be:
1.	Low bias and low variance: The predictions are not only close to actual values (low bias) but also the predictions don’t differ much in iterations when the training data is changed (low variance), so all dots are gathered around the center close to each other. This is the most desired state.
2.	Low bias and high variance: The predictions are close to actual values (low bias) but differ greatly in iterations of training with varied data (high variance), so all dots are close to center but far from each other.
