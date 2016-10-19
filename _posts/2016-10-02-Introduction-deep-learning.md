---
layout: post
title: "Introduction deep learning"
date: 2016-10-02
---

This blog is the result of a writing assignment during my data science certification. It summarizes about 40 pages of primary literature on deep learning. I chose this topic to gain first insights in deep learning. The primary literature used is referenced at the bottom of this page. 

## Management Abstract
Deep learning is a specific machine learning technique. It enables machine learning in areas where conventional methods have limited success, such as in processing images, speech or audio.
The key difference between conventional machine learning and deep learning concerns feature 'construction'. In conventional machine learning, features are human engineered. In deep learning, features are learned automatically: out of the raw-data over several abstraction layers, via computational models. 

On a high-level, deep learning uses deep graphs - graphs with many, so called hidden layers, put between an input and an output layer - to implement such a computational model. Hereby, the topology of the selected graph (e.g. how the nodes are connected, how the nodes are structured into layers), the characteristics of each node (representing a neuron) in the graph, as well as the weights on the connections between the nodes of the graph are key parameters of the computational model's design. Their role and impact is part of this blog.   
  
## Background regarding topic choice
Coming from the area of conventional machine learning this writing assignment enables first steps in the area of deep learning: 
Starting from the [1] “Deep Learning” article to get a first overview, proceeding via internet searches for related literature, as well as for deep learning hands-on tutorials. 
Relevant resources for this writing assignment are listed in the references at the bottom of this page.
Mathematical background and explanations are being kept on a minimum, instead, the focus lies on key terms, concepts and applications. 
This approach has been chosen, as many deep-learning introductions, seem to delve into mathematical explanations and notations very quickly, making it very difficult to follow the key concepts.

Based on a simplified graphical overview, the various components and their tasks in a neural network will be explained.
A real world coding example or hands-on tutorial has been post-poned, but will follow soon.  

## Summary of primary literature
Today, deep learning is often applied in the area of image-, video-, speech and audio- processing.  This is mainly because deep learning learns features automatically. Hence, features are not designed by human engineers, as in conventional machine learning techniques; instead, features are learned from data using a general-purpose learning procedure. The learning itself is an appliance of mathematical, computational models and optimizing their results.  

These computational models are composed of multiple processing layers (one input-, one output-, and zero to many hidden-layers) to learn representations of data with multiple levels of abstraction. Such abstraction levels can be obtained by composing simple but non-linear modules and each transforms the representation at one level: Starting from the raw-input (e.g. pixels of an image) into a representation at a higher, slightly more abstract level (e.g. simple objects). With the composition of enough such transformations, very complex functions can be learned.

Going one step further, the following parameters are key to deep learning and hence, such computational models: 

* The __network type/architecture/topology__ defines the number of layers, the number of neurons on each layer and if there are connections between neurons on different layers or to the neuron itself. The interconnections between neurons define which neurons can relay data to which other neurons. Different patterns produce very different network properties and possibilities. Examples of architectures are: convolutional networks or recurrent networks. A very illustrative overview on various network types can be found on [4][The Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/). 

* The __characteristics of individual neurons__ define the computation and therefore the activation function being used. Typical activation functions used in deep learning are for example sigmoid, tanh, or rectified linear unit (ReLU). The neuron collects its different inputs, calculates their sum and runs the activation function on it. The so calculated result is used as output and serves as input into the next layer.     

* The __weight-coefficients__ define how strong the connection between two neurons will be weighted. In other words, the weight-coefficient describes how the output of one neuron will be weighted as input into another neuron that is connected with the first neuron. The weight-coefficient will then be used while computing the collected and summarized input in a neuron. The weight-coefficients are the parts that are being adjusted during the training/learning epochs. After each epoch (pass over the training set) the optimal weight-coefficients have to be found automatically. Optimal in a way that the cost function has been optimized. The initialization of weight-coefficients might become key regarding how fast (or slow) the neural network learns. Especially saturated neurons - in the input layer but also in the hidden layers - slow down the process of learning. This is because saturated neurons (value close to 1 or 0) lead to small weight changes only, small weight-changes lead to miniscule changes in activation functions. As a result, the rest of the neurons will be barely affected and the changes in the cost function will be miniscule too, hence, weights will only learn very slowly (i.e. if gradient descent is used as an optimazation-method. Therefore, the initialization of weight-coefficients should be chosen in a way that this kind of saturation effect can be omitted and the learning slowdown can be avoided. One way to achieve this is the usage of sharply peaked distributions, instead of broad Gaussian distribution, as also explained in [6][Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com).      

* The __cost-function__ and its __optimization-method__ defines the function to be optimized (cost function) and how this optimization will be done (optimization-method). Typical cost functions are for example the sum of squared errors, the cross-entropy cost function or the logistic cost function. The cost-function might have a substantial impact on the way a network learns. A suboptimal choice of the cost-function might slowdown the learning process, whereas ideal cost-functions that 'produce' large errors, improve the speed a neuron will learn. Typical optimization methods are for example gradient descent or stochastic gradient descent. The key of an optimization-method is that it can be done in a very effective way. Effective means that it doesn't use too much computational time and (hopefully) converges to an optimum. To achieve this, the backpropagation algorithm is used. Backpropagation is a computationally efficient approach to compute the derivatives of a (complex) cost-function. Based on these derivatives the weight-coefficients will be learned. Instead of multiplying large matrices for each network layer (forward, from left to right), a matrix will be multiplied by a vector (backward, from right to left). A matrix vector computation is much cheaper than a matrix matrix multiplication. In other words: First, the activation of the output layer will be obtained via forward propagation (from left to right), this means that the input features will be propagated through the connections in the network. Second, the error vector of the output layer will be calculated and will then be propagated from right to left. Based on the (efficient calculation of the) error term and the computed gradient, the weight-coefficients can be updated - "the neural network is being trained and learns". 
     
The following picture provides a simplified overview on key terms explained before and how they fit into the overall picture.     

![alt text](/assets/deep-learning-overview.png "deep learning overview")

## Conclusions
Deep learning - as one specific subarea of machine learning - enables promissing solutions in areas such as image- video- or language- processing: Features will be learned automatically, instead of being engineered manually as in conventional machine learning. However, neural networks also bring along the difficulty to be set-up and adjusted in the right way. Loads of (hyper) parameters can be chosen and adjusted to improve the learning of a neural network: Improved in a way that slowing down the learning process can be omitted while keeping the computational efficiency at the same time. In this blog only key terms and parameters are explained. After first insights into general concepts, the mathematical background is key to understand why neural networks work as they work and how they can be improved. All this might make it hard to get started with deep learning and to train a neural network effectively, but current movements in the area of machine learning strongly indicate that neural networks will play an important role also in the future.    


## References 
[1] LeCun, Y., Bengio, Y., & Hinton, G. (2015). *Deep learning*. NATURE, 436-444.    
[2] LISA lab. (6. September 2016). *Deep Learning 0.1 Documentation*. [Deep Learning Tutorials](http://deeplearning.net/tutorial/)    
[3] Raschka, S. (2015). *Python Machine Learning*. In S. Raschka, Python Machine Learning (chapter 2 / chapter 12). Birmingham: Packt Publishing.    
[4] Veen, F. v. (14. September 2014). *The Neural Network Zoo*.[The Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/)     
[5] Hearty, J. (2016). *Advanced Machine Learning with Python*. In J. Hearty, Advanced Machine Learning with Python (chapter 2, part 1). Birmingham: Packt Publishing.
[6] Nielsen, M. (2016). *Neural Networks and Deep Learning*. [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com)




