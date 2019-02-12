---
title: Introduction to Bayesian Deep Learning
category: Bayesian Deep Learning
tag: BDL
---




## 0. Introduction to Bayesian Deep Learning

When it comes to **Deep Learning**, we usually think of a Neural Network.

Today, when numerous amount of training data are given, the network fully trusts the data and finds the parameters according to the data. Wouldn't this cause any problems?

Nowadays, the trend shifts to the fields of **uncertainty**. Uncertainty is when the network tells you "I don't know about this input..." When it comes to classification, not knowing a thing is also a very important issue.

So how can we measure the uncertainty, and what should we do to fully understand it?

In order to fully understand **Bayesian Deep Learning**, we need to go slowly step by step. For those who are not familiar with math especially probabilities, you should try to study them first before reading this post.

Let's look at the picture below,

<center><img src="https://i.imgur.com/3GRLRim.png"></center>

This [paper]("https://arxiv.org/abs/1703.04977") visualized the uncertainty for *Semantic Segmentation*. By using this 'uncertainty' term, we were able to decrease the noisy training data and have outstanding results. 

My goal is to post covering Bayesian Deep Learning with reference to this [paper](http://mlg.eng.cam.ac.uk/yarin/thesis/thesis.pdf).

## 1. Two Bayes Rules in Machine Learning

If you have a certain knowledge of machine learning or pattern recognition or basic probabilistic, you might be familiar with the following equation.

<center><img src="https://i.imgur.com/3GnlE1b.png"></center>

So, the equation above shows you the probability for y with given x (left). You can either use this probability for classification or regression. For example, we can select the highest probability to select or guess a class for input for classification.

But in Deep Learning point of view, you might feel something awkward. Well, there should be a network, but why are there no parameters? Of course, this is an equation for Naive Bayes classifier which has no Network Parameter. The parameters are the mean and the variance.

Let's look at the **Bayes Rule** below.

<center><img src="https://i.imgur.com/JEosdBX.png"></center>

Here, we can see a new parameter **W**. So, we can see the Y for the posterior probability shifted to the right side. What is the difference? 

Let's try to change the equation above a little bit.

<center><img src="https://i.imgur.com/7st3YLG.png"></center>


Semantically, Posterior is the probability when input and output are given while **Likelihood** is the probability of the output when the input and the parameters are given. Prior is the probability of the parameter, and evidence is the probability of the output when given the input.

Well~ for the posterior probability, this is simply the probability distribution for the parameter when the training data is given.

But, Likelihood has separate input X and output Y. This confuses us. However, if we think carefully, the probability of the output is influenced more by the parameter than the input. If the input and the output are fixed, the only thing we can manipulate is the parameter. Also, the concept of Likelihood means how much the situation can be explained.

In order to easily understand Bayes Rule, let's try to remove the input X which can be shown as follows.

<center><img src="https://i.imgur.com/4z3yi7D.png"></center>

Instead, we will combine the concept of input and the output as Dataset D, which is shown as follows.

<center><img src="https://i.imgur.com/2iGcc6K.png"></center>

The Likelihood from equation 2-a can be explained by what are the X and Parameter which can best describe Y?

The Likelihood from equation 2-c can be explained by what are the parameters which can best describe the given data?

Well, these two are eventually the same concept. 

If your interest is in the left side, Posterior, right side, Likelihood. Easy peasy~

And we should note that the prior is the distribution what we are interested in (parameters!!).

Depending on our purpose, we will want sometimes the Likelihood, sometimes the posterior. We will find the W that maximizes the likelihood and the posterior.

## 2. Maximum Likelihood Estimation(MLE) vs Maximum A Posteriori(MAP)

Before we get down to business, lets quickly cover up the basic concepts of MLE and MAP.

As mentioned earlier, P(D|W) is the **Likelihood** and we want to find the W which maximizes the likelihood. This is called **Maximum Likelihood Estimation(MLE) **, which we can think of finding the W which best describes the training data.

So our goal is to first solve P(D|W) or P(Y|X, W). How do we do this??

When we think of **Regression**, P(Y|X, W) is a Gaussian distribution which is noise. The mean is the output f(x) for the Network, which is composed of parameter W, and the variance is random. 

Then we can get the W by maximizing the likelihood given by the data.

Maximizing the Likelihood is the same with minimizing the **Mean Squared Error**.

<center><img src="https://i.imgur.com/o9bt8qi.png"></center>

For classification problem, if we consider the output as a Multi-Bernoulli distribution, maximizing the Likelihood is the same as minimizing the **Cross Entropy**.

<center><img src="https://i.imgur.com/FQSG2a9.png"></center>

Now, let's think about maximizing the posterior, which is called **Maximum A Posteriori (MAP)**. Maximizing the posterior means maximizing the Likelihood and the Prior.

<center><img src="https://i.imgur.com/VTa096h.png"></center>

This is just a thing where the Prior term is added to MLE.

This means that while solving MLE, we are additionally maximizing the probability of W while assuming that W will follow a known distribution. This is very similar to the Regularization term.


<center><img src="https://i.imgur.com/fZcdeDD.png"></center>

MLE and MAP is explained well [here](https://wiseodd.github.io/techblog/2017/01/01/mle-vs-map/)

## Bayesian Deep Learning vs Deterministic Deep Learning

Let us first go over the term of Deep Learning. The process is as follows.

  - Optimizing the parameter W with the training data.
  - The prediction for y remains fixed when W becomes fixed.
  
This means that we found W by completely trusting all the training data.

You can think that this is very similar to MLE which is maximizing the P(Y|X, W). We can solve MAP by adding the term P(W)  which W is still fixed. Because we already solved for W which maximizes the posterior. 

This is why we call this **Deterministic Deep Learning**

So what is the difference compared to **Bayesian Deep Learning**? Maybe you can understand it briefly by looking at the picture below. The left side shows the common **Deep Learning** method and the right side shows the Bayesian one.

<center><img src="https://i.imgur.com/iEOpsVX.png"></center>

We can see that Bayesian network doesn't fix the W but fixes the distribution of the W. If we think W is the value on a dice, every time we role a dice, different W pops out. This means that every time we roll a dice, different Neural Network with different W pops out!!

If you have some knowledge of deep learning, you might think this as a similar term with Model Ensembling or DropOut.

This is also true.

Back to the dice metaphor, the output now depends on the value of the dice which is random. We now might be able to solve or assume the range of the output if we can formulate an equation with the random output.

We now need P(W|D), which is the distribution of W with the given Dataset. Our goal is to know everything about W which can be done by solving the Posterior. 

Huh? Didn't we get the P(W|D) value from MAP? NOPE! We only found the W which maximizes P(W|D).

Why can't we solve P(W|D)? This is because the Marginal Likelihood should be integrated with all the W but this is very very hard to get!!

<center><img src="https://i.imgur.com/w8hhU9g.png"></center>

This is not easy to derive so we use **Variational Inference** for approximation.

We also need to solve for P(y|x) other than P(W|D).

By the Conditional Expectation equation below, we can find the distribution of the output. We should note here that we are not solving for the fixed output. We are trying to get the distribution of the output.

<center><img src="https://i.imgur.com/B80rLyE.png"></center>

But this is also not easy which needs **Sampling** or additional **Approximation** or etc. I will try to introduce one of the techniques for this.

>TLDR

  - Machine Learning's goal is to find W and predict Y
  - Non=Bayesian Deep Learning is to find the fixed W value and predict the fixed Y
  - Bayesian Deep Learning's goal is to get the distribution of W (P(W|D)) while also predicting the distribution of Y (P(Y'|X', W).
  
  
For future work, I will cover
  - So how on earth do we get the probability P(W|D)
  - How do we get P(Y'|X', W)
  - How do we get the uncertainty and where can we use it??
  
