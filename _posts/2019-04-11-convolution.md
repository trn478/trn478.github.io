---
title: Convolutional Neural Networks (CNNs)
---

**What is Convolutional Neural Networks (CNNs)?**
----------

Convolutional neural network are used to find patterns in a given image. Through convolution over an image, for pixels in rows and columns of the image, seeking suitable patterns. Layers in CNNs that helps the model identify images. 

![](<../images/cnns.jpg>)

Source : [CSC231](http://cs231n.github.io/convolutional-networks/)

**Quick Shout out - Founder of CNNs**
----------
[**Geoffrey Hinton**](http://www.cs.toronto.edu/~hinton/) 

- Chief Scientific Advisor, Vector Institute 

- Vice President and Engineering Fellow, Google 

- Emeritus Distinguished Professor of Computer Science, University of Toronto 


**What does Convolutional Neural Networks do?**
-------------------

Through convolution over an image, for pixels in rows and columns of the image, seeking suitable patterns.
Layers in CNNs that helps the model identify images. To elaborate, in the first few layers of CNNs, the network identifies 
 lines and corners. Then, we pass these patterns to the next layer through neural networks and start recognizing more complex 
 features as we get deeper into the neural network. This is similar to how our own brain works. We first identify the 
 appearance of the object and then classify it, based on the complex knowledge in our memory. The ability to use multiple 
 layers makes CNNs exceptional at detecting objects in high dimensional images.

**Where is it used?**
-------------------

CNNs was a major breakthrough for AI, it has made massive improvements possible for certain stagnant fields of Machine Learning, such as neural network. CNNs enabled developers with the capability of providing the end-user with more personalized products and services.

## Main Fields using CNN

1) **Self-driving** cars using Object detection

2) **Personalized** Medicine

3) **Recommendation** Programs used by YouTube, Amazon, Netflix, etc.

4) Natural Language Processing (**NLP**)


**Layers in CNNs**
-------------------
1) Convolution Layer 

2) Pooling Layer

3) Activation Layer 

To understand how CNNs works, we must learn about convolutions. But, what are convolutions? 

**Convolutions & Convolution Layer**
-------------------

**Convolutions** involve iterating through each pixels of the image and applying filter to find some patterns.

![](<../images/convgif.gif>)

Source : [NYU](https://cs.nyu.edu/~fergus/tutorials/deep_learning_cvpr12/)

There is an image represented by 7x7, 7 pixels by 7 pixels, 
matrix of value. Now you can take 3x3 matrix of value and move over the image, multiplying the 3x3 matrix with window of 
the image to generate a single value. Then, the 3x3 matrix moves to right and down to iterate through the entire image. 
This 3x3 matrix is called a kernel. The convolved feature will be represented as 3x3 matrix with the values generated 
through the kernel. The purpose of a convolution layer is to filter. As we iterate through an image we effectively check 
for patterns in that particular section of the image. This is done through filters, stacks of weight represented in vector 
form, which are multiplied by the values outputted by the convolution.

**Pooling Layer & Problems related to CNNs**
-------------------
The layer in-between successive convolution layers in CNNs architecture is called the **pooling layer**. It partitions the input 
image into non-overlapping rectangles and, for each partition, outputs a value. The intuition behind the pooling layer is that 
the exact location of a feature is less important than its rough location relative to other features.
 
 ![](<../images/max-pool.png>)
 
 Source : [CSC231](http://cs231n.github.io/convolutional-networks/)
 
 Suppose you are watching a movie in a theater. You don’t look at each pixel on the screen but rather look at sub regions of the screen to understand what 
is going on. The same applies to the pooling layer. The two main pooling layers are a maximum pooling layer and an average pooling 
layer. The maximum pooling layer outputs the maximum value of the sub region. The average pooling layer computes the average value 
of the sub region. Since CNN deals with many layers, data are organized in high dimensional spaces. When analyzing data in high 
dimensional spaces, an analyst suffers from **“the curse of dimensionality”**. 

The curse of dimensionality refers to various phenomena that arise when analyzing data in high dimensional spaces that do not occur 
in low dimensional settings, such as three dimensional 
 physical space. We use the pooling layer to solve this problem and further **reduce spatial dimensions**. 
 
 ![](<../images/overfit.png>)
 
 The main benefits of reducing 
 spatial dimensions are immensely improved computational performance. Furthermore, you have less parameters to train the model on,
  thus reducing the chances of **over-fitting**, which is a major problem for training any machine learning models. Briefly, over-fitting 
  is: the artifact of an analysis that corresponds too closely to a particular set of data and, therefore, fails to fit additional data
   or predict future observations reliably. The pooling layer improves prediction by reducing spatial dimensions and over-fitting, 
   thus improving the overall reliability of the model.
   
   You can learn more about **over-fitting** [here](https://medium.com/predict/what-overfitting-is-and-how-to-fix-it-887da4bf2cba)
   

**Activation Layer**
-------------------
 Activation layers pass values through a function that squashes the value into a range. 
 The most common activation function is the **ReLu** activation function.
 
  ![](<../images/relu.png>)
  
  Source : [Medium](https://towardsdatascience.com/activation-functions-neural-networks-1cbd9f8d91d6)
  
  ReLu function takes an input and returns the input if the input is positive else return zero. 
  ReLu is extremely cheap to perform and, thus commonly used in development of deep learning models
  
**Success of CNNs**
-------------------
It is not an overstatement that the recent surge of interest in deep learning is due to the immense popularity and 
effectiveness of CNNs. The interest in CNNs started with AlexNet in 2012 and has grown ever since. 
It took only 3 years for researchers to progress from **8 layer AlexNet to 152 layer ResNet**.
 Imagine how extraordinarily accurate a neural network can be with 152 layers! 

**Summary**
------------------
-   Perform convolution on an image with a ReLU activation layer to the matrix. 

-   ReLU is extremely cheap and speeds up computations

-   Pooling layer reduces dimensionality size, thus reduces **"the curse of dimensionality"**

-   Add convolution layers until you are satisfied with the result 

**Key Takeaway**
------------------
-   CNNs represents a major accomplishment for Artificial Intelligence and will be used well into the future. Understanding how CNNs models operate can help us understand how we learn as human beings.

-   CNNs is and will be the main building block for many life-changing technological improvements in the upcoming years.






