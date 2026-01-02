---
title: "Ch 1: Introduction to Deep Learning"
date: 2025-12-15
tags:
  - deep-learning-python
  - dl
---

# Ch 1: What is deep learning?

Notes from *Deep Learning with Python* by François Chollet.

## Artificial Intelligence

at Dartmouth College in 1956, John McCarthy organized a summer workshop based on the conjecture that every aspect of learning and intelligence could be precisely described and simulated by a machine. this event is recognised as the birth of AI. at the end of the summer, the workshop concluded without having fully solved the riddle it set out to investigate.
many pioneers attended this event, including Marvin Minsky, Claude Shannon, and Allen Newell.

from 1950s to 80s AI research was dominated by symbolic AI, which focused on building systems that could reason and learn like humans. for a fairly long time, most experts believed that human-level artificial intelligence could be achieved by having programmers handcraft a sufficiently large set of explicit rules for manipulating knowledge stored in explicit databases.

AI is a general field that encompasses machine learning and deep learning. AI can be described as an effort to automate intellectual tasks normally performed by humans. 

## Machine Learning
The usual way to make a computer do useful work is to have a human programmer write down rules - a computer program - to be followed to turn input data into appropriate answers, just like Lady Lovelace writing down step-by-step instructions for the Analytical Engine to perform. Machine learning turns this around: the machine looks at the input data and the corresponding answers, and figures out what the rules should be.

<p align="center" width="100%">
    <img width="70%" src="assets/dl_chollet/ch1/a-new-programming-paradigm.e8d1a1c2.png">
</p>

you do not program a machine learning system, you train it. you make the model see a lot of data and let it learn from it by finding patterns in the data.\
ML started to flourish in the 1990s. Machine learning is related to mathematical statistics, but it differs from statistics in several important ways — in the same sense that medicine is related to chemistry but cannot be reduced to chemistry, as medicine deals with its own distinct systems with their own distinct properties. Unlike statistics, machine learning tends to deal with large, complex datasets (such as a dataset of millions of images, each consisting of tens of thousands of pixels) for which classical statistical analysis such as Bayesian analysis would be impractical.

## Learning rules and representations from data
To do ML, you need 3 things : 
1. input data points
2. examples of expected output
3. a way to measure whether algorithm is doing good or bad - we check how far off the algorithm is from actual. then we use this as a feedback to improve the algorithm. this step is called *learning*\

machine learning model transforms its input data into meaningful outputs, a process that is “learned” from exposure to known examples of inputs and outputs. Therefore, the central problem in machine learning and deep learning is to meaningfully transform data.\
but what is representation exactly? representation is a way to encode data in a way that is meaningful to the model. for instance, a color image can be encoded in the RGB format (red-green-blue) or in the HSV format (hue-saturation-value): these are two different representations of the same data. ML models are all about finding appropriate representations for their input data.\
Some tasks that may be difficult with one representation can become easy with another. For example, the task “Select all red pixels in the image” is simpler in the RGB format, whereas “Make the image less saturated” is simpler in the HSV format.

> Concrete example :

so consider a sample data as shown below :
<p align="center" width="25%">
    <img height="20%" width="20%" src="assets/dl_chollet/ch1/sample_data.png">
</p>

Let’s say we want to develop an algorithm that can take a point’s (x, y) coordinates and output whether that point is likely black or white. In this case,
1. The inputs - the coordinates of our points.
2. The expected outputs - the colors of our points.
3. A way to measure whether our algorithm is doing a good job - the percentage of points that are being correctly classified.

we need new representation of our data that cleanly separates the white points from the black points. one transformation we could use, among many other possibilities, would be a coordinate change.
<p align="center" width="75%">
    <img width="75%" src="assets/dl_chollet/ch1/sample_data_2.png">
</p>

With this representation, the black/white classification problem can be expressed as a simple rule: **“Black points are such that x > 0,” or “White points are such that x < 0.”**

But in this case, we defined coordinate change by hand because the task was simple. Could you do the same if the task were to classify images of handwritten digits? Could you write down explicit, computer-executable image transformations that would illuminate the difference between a 6 and an 8, between a 1 and a 7, across all kinds of different handwritings ?

## Deep Learning

### "deep" in deep learning
subset of ML, which emphasizes learning successive layers of increasingly meaningful representations. How many layers contribute to a model of the data is called the depth of the model. The “deep” in “deep learning” isn’t a reference to any kind of deeper understanding achieved by the approach; rather, it stands for this idea of successive layers of representations.

In DL, these layered representations are learned via models called neural networks, structured in literal layers stacked on top of each other.

Let’s examine how a network several layers deep transforms an image of a digit to recognize what digit it is.

<p align="center" width="75%">
    <img width="75%" src="assets/dl_chollet/ch1/dl_eg1.png">
</p>

As you can see in figure below, the network transforms the digit image into representations that are increasingly different from the original image and increasingly informative about the final result.

<p align="center" width="75%">
    <img width="75%" src="assets/dl_chollet/ch1/dl_eg2.png">
</p>

You can think of a deep network as a multistage information-distillation process, where information goes through successive filters and comes out increasingly purified

### understanding how deep learning works, in three figures

The specification of what a layer does to its input data is stored in the layer’s weights, which in essence are a bunch of numbers. Transformation implemented by a layer is parameterized by its weights. In this context, learning means finding a set of values for the weights of all layers in a network, such that the network will correctly map example inputs to their associated targets.

So, now the question is how do we find the right values for the weights ?
First, we need a way to measure how good the network is at its job. For this we calculate a loss value, which essentially means to measure how far model output is from expected output. This is known as loss function of network or objective function or cost function. 

Loss function is a function that takes as input the model’s prediction and the target value, and returns a single number estimating how far off the prediction was from the target.

<p align="center" width="75%">
    <img width="75%" src="assets/dl_chollet/ch1/understanding_dnn.png">
</p>

Loss score is used to as a feedback signal to adjust the weights such that we lower the loss score. This adjustment is the job of the optimizer, which implements what’s called the Backpropagation algorithm. 

<p align="center" width="75%">
    <img width="75%" src="assets/dl_chollet/ch1/understanding_dnn2.png">
</p>

But when we begin the model training we have no loss score, then how do we initialise the weights ? Well, we begin by setting the weights to random values, so the network merely implements a series of random transformations. Naturally, its output is far from what it should ideally be, and the loss score is accordingly very high. But with every example the network processes, the weights are adjusted a little in the correct direction, and the loss score decreases. This is the training loop, which, repeated a sufficient number of times (typically tens of passes over thousands of examples), yields weight values that minimize the loss function. A network with a minimal loss is one for which the outputs are as close as they can be to the targets: a trained network.

## What makes deep learning different ?
- simplicity : with deep learning, you learn all features in one pass rather than having to engineer them yourself (feature engineering)
- scalability : deep learning is highly amenable to parallelization on GPUs or more specialized machine learning hardware, so it can take full advantage of Moore’s law
- versatility and reusability : deep learning models can be trained on additional data without restarting from scratch, making them viable for continuous online learning

## Age of Generative AI
ChatGPT, Gemini, and Claude or Midjourney. 

Generative AI is powered by very large “foundation models” that learn to reconstruct the text and image content fed into them — reconstruct a sharp image from a noisy version, predict the next word in a sentence, and so on. This means that the targets from figure 1.8 are taken from the input itself. This is referred to as self-supervised learning, and it enables those models to use vast amounts of unlabeled data. Doing away with the manual data annotations that bottlenecked previous brands of machine learning has unlocked a level of scale never seen before — some of these foundation models have hundreds of billions of parameters and are trained on over 1 petabyte of data, at the cost of tens of millions of dollars.

These foundation models operate as a kind of fuzzy database of human knowledge, making them amenable to a very wide range of applications without needing special-purpose programming or retraining. Because they’ve already memorized so much, they can solve new problems merely via prompting — querying the knowledge representations they’ve learned and returning the output most likely to be associated with your prompt.