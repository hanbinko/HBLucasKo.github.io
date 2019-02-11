'''
title: Introduction to Bayesian Deep Learning
category: Bayesian Deep Learning
tag: BDL
'''

## 0. Introduction to Bayesian Deep Learning

There are various kinds of Deep Learning, and we usually think of Neural Network.

Today, when numerous amount of training datas are given, the network fully trusts the data and finds the parameters according to the data. Woudn't this cause any problems?

Nowadays, the trend shifts to the fields of uncertainty. Uncertainty is when the network tells you "I don't know about this input..." When it comes to classification, not knowing a thing is also a very important issue.

So how can we measure the uncertainty, and what should we do to fully understand it?

In order to fully understand **Bayesian Deep Learning**, we need to go slowly step by step. For those who are not familiar with math especially probabilities, you should try to study them first before reading this post.

Let's look at the picture below,

<center><img src='public/img/1.png'></center>
