## Introduction

The ResNet architecture is considered to be among the most popular Convolutional Neural Network architectures around. 
Introduced by Microsoft Research in 2015, Residual Networks (ResNet in short) broke several
records when it was first introduced in this paper by He. et. al.

## Why ResNet?

The requirement for a model like ResNet arose due to a number of pitfalls in modern networks at the time.

## 1. Difficulty in training deep neural networks:
   
As the number of layers in a model increases,
the number of parameters in the model increases exponentially. For each Convolutional layer, 
To put it into context, a simple 7x7 kernel Convolution layer from 3 channels to 32 channels adds 4736 parameters.
An increase in the number of layers in the interest of experimentation leads to an equal increase
in complexity for training the model. Training then requires greater computational power and memory.

## 2.More expressive, less different:

A neural network is often considered to be a function approximator. 
It has the ability to model functions given input, target and a comparison between the function output and target. 
Adding multiple layers into a network makes it more capable to model complex functions.
But results published in the paper stated that a 18-layer plain neural network performs considerably better than a 34-layer plain neural network

## 3. Vanishing/Exploding Gradient:

This is one of the most common problems plaguing the training of larger/deep neural networks and is a result of oversight
in terms of numerical stability of the network’s parameters.
During back-propagation, as we keep moving from the deep to the shallow layers,
the chain rule of differentiation makes us multiply the gradients. Often, these gradients are small

## ResNet Architecture

![resnet50](https://github.com/abijith-tk/DeepLearning/assets/113427408/612b8ecd-2c27-4afc-96ab-0b56715297aa)

