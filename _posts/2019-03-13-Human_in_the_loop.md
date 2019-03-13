---
title: Introduction to Human-In-The-Loop
category: Human-In-The-Loop
tag: HIL
---


## 0. Introduction to Human-in-the-Loop

Nowadays, **machine learning**, and **deep learning** is becoming more and more mainstream, and a lot of companies and startups try to use these algorithms for their projects. However, building a dataset for the project is very expensive and a lot of workers and researchers are trying to make this process more efficient. One of this practice is called **“human-in-the-loop” ** computing.

Human-in-the-loop process can be simply explained as a loop when machine relies on human and adds human judgment to its model when it isn’t sure what the answer is. This simple pattern is at the heart of many well-known, real-world use of cases in deep learning. Also, it is awesome because it solves one of the biggest issues with machine or deep learning, namely: it’s often very easy building an algorithm to 80 percent accuracy but often impossible to get an algorithm to 99 percent. The best model lets humans handle the 20 percent since 80 percent accuracy is not satisfactory enough for most of the real-world applications. Let’s look at some examples.

<center><img src=”https://i.imgur.com/B6wrT0L.jpg”></center>

#### Self-driving cars

Self-driving cars are a great example of implementing “human-in-the-loop” in deep learning. A lot of smart people had been working on smart cars for a very long time and the state-of-the-art tech is actually pretty good. However, the biggest problem is that even though if a model achieves 99% in accuracy, this means that for 1% failure, a person might die.

Tesla is launching an automating driving mode that followed exactly the human-in-the-loop pattern. The car mostly drives itself on highways but insists that the human should keep their hands on the wheel for emergency. When the deep learning intelligent system senses doubt or uncertainty- maybe snow, strong illumination, or something the car has never seen before- it hands the control back to the human driver. So while the car can indeed drive itself almost at all times, it still needs human assistance.

<center><img src=”https://i.imgur.com/dOMkiIj.png”></center>


#### Labeling images in Facebook

Facebook’s photo recognition algorithm has gotten crazy good! In fact, Facebook recognizes almost any photos you upload with high accuracy. But in cases where its confidence is below a certain threshold, Facebook will ask us (the uploader) to confirm the person or things labeled in the photo. Also, in cases where the confidence level is even lower, it will ask us the label the photo ourselves. All these data are fed back in to their algorithm to get better and better.

#### Building datasets for deep learning models

Obtaining large dataset is very expensive due to large amount of annotations. If the machine can just ask where to annotate this will reduce a lot of work. Recently a lot of researchers are working on **active learning**, which the machine itself learns where it needs more information and asks the oracle (human annotator) to give labels for it. By achieving this method, we can use deep learning even with small datasets.

<center><img src=”https://i.imgur.com/TZENn51.png”></center>


## 1. Summary

We could see that human-computer interaction is much more important for artificial intelligence than we ever thought. Making sure computers and humans work well together is critical for all or the applications to work. Therefore human-in-the-loop process is very important now and in the future. 

Artificial intelligence is here and it’s changing every aspect every dat. But we should know that it’s not replacing one’s job but making people in every job more efficient by being an assistant handling the easy cases and watching and learning from the hard cases. 
