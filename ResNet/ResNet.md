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



## What Is the ResNet-50 Model?


ResNet stands for Residual Network and is a specific type of convolutional neural network (CNN)
introduced in the 2015 paper "Deep Residual Learning for Image Recognition" by He Kaiming, Zhang
Xiangyu, Ren Shaoqing, and Sun Jian. CNNs are commonly used to power computer vision
applications.
ResNet-50 is a 50-layer convolutional neural network (48 convolutional layers, one MaxPool layer, and
one average pool layer). Residual neural networks are a type of artificial neural network (ANN) that
forms networks by stacking residual blocks.


## ResNet-50 Architecture

The original ResNet architecture was ResNet-34, which comprised 34 weighted layers. It provided a
novel way to add more convolutional layers to a CNN, without running into the vanishing gradient
problem, using the concept of shortcut connections. A shortcut connection "skips over" some layers,
converting a regular network to a residual network.
The regular network was based on the VCC neural networks (VCC-16 and VCC-19)—each convolutional
network had a 3x3 filter. However, a ResNet has fewer filters and is less complex than a VCCNet. A 34-
layer ResNet can achieve a performance of 3.6 billion FLOPs, and a smaller 18-layer ResNet can achieve
1.8 billion FLOPs, which is significantly faster than a VCC-19 Network with 19.6 billion FLOPs (read more
in the ResNet paper, He et,Ä, 2015).
The ResNet architecture follows two basic design rules. First, the number of filters in each layer is the
same depending on the size of the output feature map. Second, if the feature map's size is halved, it
has double the number of filters to maintain the time complexity of each layer.

## Special characteristics of ResNet-50

ResNet-50 has an architecture based on the model depicted above, but with one important difference.
The 50-layer ResNet uses a bottleneck design for the building block. A bottleneck residual block uses
1 xl convolutions, known as a "bottleneck", which reduces the number of parameters and matrix
multiplications. This enables much faster training of each layer. It uses a stack of three layers rather
than two layers.
The 50-layer ResNet architecture includes the following elements, as shown in the table below:
- A 7x7 kernel convolution alongside 64 other kernels with a 2-sized stride.
- A max pooling layer with a 2-sized stride.
- 9 more layers—3x3,64 kernel convolution, another with 1,64 kernels, and a third with lx1,256
kernels. These 3 layers are repeated 3 times.
- 12 more layers with kernels, 3x3t128 kernels, and kernels, iterated 4 times.
- 18 more layers with lx1t256 cores, and 2 cores 3x3t256 and iterated 6 times.
- 9 more layers with cores, 30,512 cores, and cores iterated 3 times.
(up to this point the network has 50 layers)
- Average pooling, followed by a fully connected layer with 1000 nodes, using the softmax activation
function.
