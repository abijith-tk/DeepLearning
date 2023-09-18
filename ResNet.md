# Residual Networks (ResNet) – Deep Learning

A Residual Neural Network (a.k.a. Residual Network, ResNet) is a deep learning model in which the weight layers learn residual functions with reference to the layer inputs. 
A Residual Network is a network with skip connections that perform identity mappings, merged with the layer outputs by addition.
It behaves like a Highway Network whose gates are opened through strongly positive bias weights. 
This enables deep learning models with tens or hundreds of layers to train easily and approach better accuracy when going deeper. 
The identity skip connections, often referred to as "residual connections", are also used in the 1997 LSTM networks,[3] Transformer models (e.g., BERT, GPT models such as ChatGPT),
the AlphaGo Zero system, the AlphaStar system, and the AlphaFold system.

Residual Networks were developed by Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun, which won the ImageNet 2015 competition.

Residual Network: In order to solve the problem of the vanishing/exploding gradient, this architecture introduced the concept called Residual Blocks. In this network, we use a technique called skip connections. The skip connection connects activations of a  layer to further layers by skipping some layers in between. This forms a residual block. Resnets are made by stacking these residual blocks together. 
The approach behind this network is instead of layers learning the underlying mapping, we allow the network to fit the residual mapping. So, instead of say H(x), initial mapping, let the network fit, 

# F(x) := H(x) - x which gives H(x) := F(x) + x. 

![Residual Block](https://media.geeksforgeeks.org/wp-content/uploads/20200424011510/Residual-Block.PNG)

The advantage of adding this type of skip connection is that if any layer hurt the performance of architecture then it will be skipped by regularization. So, this results in training a very deep neural network without the problems caused by vanishing/exploding gradient.  The authors of the paper experimented on 100-1000 layers of the CIFAR-10 dataset. 
There is a similar approach called “highway networks”, these networks also use skip connection. Similar to LSTM these skip connections also use parametric gates. These gates determine how much information passes through the skip connection. This architecture however has not provided accuracy better than ResNet architecture. 

