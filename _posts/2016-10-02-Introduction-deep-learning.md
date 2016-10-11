---
layout: post
title: "Introduction deep learning"
date: 2016-10-02
---

This blog is the result of a written assignment during my data science certification. It summarizes about 40 pages of primary literature on deep learning. I chose this topic to gain first insights in deep learning. The primary literature I used is referenced at the bottom of this page. 

## Management Abstract
Deep learning is a specific machine learning technique. It enables machine learning in areas where conventional methods have limited success, such as in processing images, speech or audio.
The key difference between conventional machine learning and deep learning concerns feature 'construction'. In conventional machine learning, features are human engineered. In deep learning, features are learned automatically: out of the raw-data over several abstraction layers, via computational models. 

On a high-level, deep learning uses deep graphs - graphs with many, so called hidden layers, put between an input and an output layer - to implement such a computational model. Hereby, the topology of the selected graph (e.g. how the nodes are connected, how the nodes are structured into layers), the characteristics of each node (representing a neuron) in the graph, as well as the weights on the connections between the nodes of the graph are key parameters of the computational model's design. Their role and impact is part of this blog.   
  
## Why did I choose this topic?
As I have read already quite a lot in the area of conventional machine learning, but haven’t tried yet to get into the topic of deep learning, I wanted to seize the opportunity of this writing assignment to make first baby steps in this area. 
I started with the [1] “Deep Learning” article to get a first overview. From there, I searched the internet for related literature, as well as for deep learning hands-on tutorials. All relevant resources are listed in the references at the bottom of this page.
I tried to keep mathematical background and explanations on a minimum (or even avoid it), but focus on key terms, concepts and applications instead. This mainly because many introductions, I've come across, dive into mathematical explanations and notations, which make it very difficult to follow for someone who is new to this topic.

Based on a very simple graphical overview, I try to explain the various components and their tasks in a neural network. First, I wanted to enhance the explanations with some code snippets from a hands-on tutorial, but so far I'm still working on the context and general perspectives. Therefore, the hands-on part has been post-poned, but hopefully will follow soon.  

## Summary of primary literature
Today, deep learning is often applied in the area of image-, video-, speech and audio- processing.  This is mainly because deep learning learns features automatically. Hence, features are not designed by human engineers, as in conventional machine learning techniques; instead, features are learned from data using a general-purpose learning procedure. The learning itself is an appliance of mathematical, computational models and optimizing their results.  

These computational models are composed of multiple processing layers (one input-, one output-, and zero to many hidden-layers) to learn representations of data with multiple levels of abstraction. Such abstraction levels can be obtained by composing simple but non-linear modules and each transforms the representation at one level: Starting from the raw-input (e.g. pixels of an image) into a representation at a higher, slightly more abstract level (e.g. simple objects). With the composition of enough such transformations, very complex functions can be learned.

If we go one step further, the following parameters are key to deep learning or such computational models: 

* The __network type/architecture/topology__ defines the number of layers, the number of neurons on each layer and if there are connections between neurons on different layers or to the neuron itself. The interconnections between neurons define which neurons can relay data to which other neurons. Different patterns produce very different network properties and possibilities. Examples of architectures are: convolutional networks or recurrent networks. A very illustrative overview on all sorts of network types can be found on [The Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/). 

* The __characteristics of individual neurons__ define the computation and therefore the activation function that is being used. Typical activation functions used in deep learning are for example sigmoid, tanh, or rectified linear unit (ReLU). The neuron collects all different inputs, builds the sum on them and runs the activation function on this input-sum. The output is then used as input into the next layer.     

* The __weight-coefficients__ define how strong the connection between two neurons will be weighted. In other words, the weight-coefficient describes how the output of one neuron will be weighted as input into another neuron that is connected with the first neuron. The weight-coefficient will then be used while computing the collected and summarized input in a neuron. The weight-coefficients are the parts that are being adjusted during the training/learning epochs. After each epoch (pass over the training set) the optimal weight-coefficients have to be found automatically. Optimal in a way that the cost function has been optimized.  

* The __cost-function__ and its __optimization-method__ defines what has to be optimized (cost function) and how this optimization as to be done (optimization-method). Typical cost functions are for example the sum of squared errors or ... . Typical optimization methods are for example gradient descent or stochastic gradient descent. The key of an optimization method is that it can be done in a very effective way. Effective means that it doesn't use too much computational time and (hopefully) converges to an optimum. 
     
As a simplified introduction, the following picture provides an overview on key terms, their meaning and how they fit into the overall picture.     

![alt text](/assets/deep-learning-overview.png "deep learning overview")

## Conclusions
Thanks to this written assignment, I overcame my inhibition threshold towards deep learning and I now feel up to tackle new types of machine learning topics, such as for example image recognition. For me it was key to get clarification on terms and their meanings first. Mathematical explanations and backgrounds remain challenging and before diving into mathematical explanations I will start with a hands-on tutorial to find out, how things work. Finally, the mathematical background will (hopefully) give me insights why things work as they work. 

I started off with the [1]“Deep Learning” article, which provides a good starting point to dive into this topic; It outlines the different network types (neuronal, convolutional and recurrent) and puts deep learning in the context of machine learning techniques, including its pros and cons. Additional resources were then needed to strengthen and broaden first insights and understandings. Resources that helped me most to achieve this are listed below. 

## References 
[1] LeCun, Y., Bengio, Y., & Hinton, G. (2015). *Deep learning*. NATURE, 436-444.    
[2] LISA lab. (6. September 2016). *Deep Learning 0.1 Documentation*. [Deep Learning Tutorials](http://deeplearning.net/tutorial/)    
[3] Raschka, S. (2015). *Python Machine Learning*. In S. Raschka, Python Machine Learning (chapter 2 / chapter 12). Birmingham: Packt Publishing.    
[4] Veen, F. v. (14. September 2014). *The Neural Network Zoo*.[The Neural Network Zoo](http://www.asimovinstitute.org/neural-network-zoo/)     
[5] Hearty, J. (2016). *Advanced Machine Learning with Python*. In J. Hearty, Advanced Machine Learning with Python (chapter 2, part 1). Birmingham: Packt Publishing.




