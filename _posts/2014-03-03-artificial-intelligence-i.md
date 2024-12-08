---
layout: post
title: "Artificial Intelligence I"
categories: AI
tags: AI ML GAN
---

* TOC
{:toc}

"US Copyright Office Issues Rules For Generative AI"
<iframe width="560" height="315" src="https://www.youtube.com/embed/y1LAvIJJP88?controls=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

[U.S. Copyright Office Rules A.I. Art Can’t Be Copyrighted](https://www.smithsonianmag.com/smart-news/us-copyright-office-rules-ai-art-cant-be-copyrighted-180979808/)

https://github.com/terryum/awesome-deep-learning-papers

narrow AI, what we currently have altogether as of 2024

categories based on human interactions

- assisted intelligence AI, such as speech recognition
- augmented intelligence, such as Siri and Alexa
- autonomous intelligence AI, such as self-driving cars

categories based on function

- reactive AI, such as games
- limited memory AI, such as self-driving cars

generative AI is an augmented intelligence, limited-memory AI that uses deep learning by utilizing LLMs

strong AI, includes theory of mind AI (some progress on this) and self-aware AI (purely speculative)

issues/problems: accuracy, specifically: bias, hallucinations, false facts

Get useful / meaningful data.

Regression helps the computer predict something after knowing some dataset. 

Preprocessing is cleaning.

Features are descriptive attributes, labels are what you’re trying to predict or forecast.

Supervised learning is teaching the computer based on labeled training data.

Building neural networks -> build neurons

Neurons are sigmoid functions. Sigmoid functions are activation functions. A neuron has all of the activations from previous layers and each activation has its own weight (evolves during training) and bias (a constant value). 

Each set of sigmoid function connection is a layer. The process of generating an output given an input is called forward propagation. Output of the final layer is called prediction and cost function. The goal is to reduce the cost function. The value of the cost function shows the difference between predicted value and truth value. Algorithms such as gradient descent and stochastic gradient descent updates the parameter of the neural network.

"The "K-means clustering algorithm" is an algorithm for grouping a set of data points into clusters based on their similarity."

"The "Hierarchical clustering algorithm" is an algorithm for grouping a set of data points into a hierarchical structure based on their similarity."

["FrontierMath: A Benchmark for Evaluating Advanced Mathematical Reasoning in AI"](https://arxiv.org/html/2411.04872v1)



AI competes with natural intelligence 

AI Value Chain

  - Data
  - Chips
  - Platform & Infrastructure
  - Models & Algorithms
  - Enterprise Solutions
  - Corporates
  - Nations

Provide the best vertical solutions via your own startup



> "Every time we figure out a piece of it, it stops being magical; we say, 'Oh, that's just a computation.'" 
> Rodney Brooks on AI effect



Important basics in order:

1. Linear algebra, probability, algorithms, calculus
2. Python, tensorflow
3. Deep learning



## 



## Neural Networks

"The "Backpropagation" algorithm is a widely used algorithm for training neural networks, which involves adjusting the weights of the connections between neurons in order to minimize the error of the network's predictions."

"The "Self-Organizing Map" is a type of neural network that is used for unsupervised learning and which is based on the idea of mapping input data onto a two-dimensional grid of neurons."

"The "Autoencoder" is a type of neural network that is used for unsupervised learning and which is designed to reconstruct its input data as accurately as possible."

"Keras is a high-level, open-source neural network library written in Python. It is designed to make it easier to build, train, and deploy deep learning models. Keras is built on top of other popular machine learning libraries such as TensorFlow, Theano, and CNTK, and provides a simple, user-friendly interface for working with these libraries.

Apache Spark is an open-source, distributed computing system that is designed for large-scale data processing. It is often used for big data and machine learning workloads, and provides a variety of tools for working with data, including a machine learning library called MLlib. Spark is written in Scala, but has APIs in various programming languages including Python, so it can be used with Keras and other Python libraries."

Perceptron

Activation Functions

Cost Functions

Gradient Descent Backpropagation



## Machine Learning Algorithms

["The Definitive Security Data Science and Machine Learning Guide"](http://www.covert.io/the-definitive-security-datascience-and-machinelearning-guide/)

["Machine Learning and Security"](http://www.mlsec.org)

"The "Decision Tree" is a machine learning algorithm that is used for classification and regression tasks."

"The "Random Forest" is a machine learning algorithm that is used for classification and regression tasks, and which is based on the idea of combining the predictions of multiple decision trees."

"The "Transfer Learning" is a technique in machine learning that involves using a pre-trained model as a starting point for a new task, rather than training a model from scratch."

"The "Active Learning" is a technique in machine learning that involves selecting the most informative data for a model to learn from, in order to improve its performance."

"The "Reinforcement Learning" is a type of machine learning that involves an agent learning by interacting with its environment and receiving rewards or penalties for certain actions."

"The "Q-learning" is a type of reinforcement learning algorithm that involves an agent learning a policy for maximizing its expected reward through trial and error."

ML -> Deep Learning



### Supervised Learning

"Supervised learning involves training a machine learning model on labeled data, in which the correct output is provided for each example in the training set."



### Unsupervised Learning

"Unsupervised learning involves training a model on unlabeled data, in which the model must discover the underlying structure of the data in order to make predictions."



### Semi-supervised Learning

"Semi-supervised learning involves training a model on a combination of labeled and unlabeled data."



### Reinforcement Learning

"Reinforcement learning involves training a model to make decisions in an environment in order to maximize a reward."



### Support Vector Machines (SVMs)

"The "Support Vector Machine" is a machine learning algorithm that is used for classification and regression tasks."



### Boosting



### K-Nearest Neighbors (KNN)



## Deep Learning Algorithms



### Convolutional Neural Networks (CNNs)

"The "Convolutional Neural Network" is a type of neural network that is particularly well-suited for processing data with a grid-like structure, such as images or time series data."

image recognition algorithm



### Recurrent Neural Networks (RNNs)

"The "Recurrent Neural Network" is a type of neural network that is particularly well-suited for processing sequential data, such as natural language or time series data."



### Generative Adversarial Networks (GANs)

"Generative Adversarial Networks (GANs) are a type of artificial intelligence algorithm that uses two neural networks, a generator and a discriminator, to generate new data samples that are similar to a training dataset. The generator network generates synthetic data samples, while the discriminator network attempts to distinguish the synthetic samples from real samples in the training dataset.

During training, the generator and discriminator networks compete with each other, with the generator trying to produce synthetic samples that are similar enough to the real samples to fool the discriminator, and the discriminator trying to accurately identify the synthetic samples. This competition drives the generator to produce increasingly realistic synthetic samples.

Once trained, the generator network can be used to generate new data samples that are similar to the training dataset. This can be useful in a variety of applications, such as generating realistic images, audio samples, or other types of data."



## Natural Language Processing 

NLP deals with programming computers to handle natural language data



Natural Language Search (NLS)



## Computer Vision



### Image segmentation algorithms



### Feature extraction algorithms



### Object detection algorithms



### Object tracking algorithms



### Face recognition algorithms



## Robotics



## Swarm Intelligence

SI collective behavior of decentralized, self-organized systems


