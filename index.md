---
title       : Neural Networks
subtitle    : A really brief introduction
author      : Tommy Shen
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---&twocol w1:60% w2:40%
## A more challenging problem
*** left

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1.png) 


*** right

- How would we classify this problem with the methodologies we've learned thus far?
  * KNN
  * Naive Bayes
  * Regression
  * Trees

--- 
## Gateway to Complex Modeling
Neural nets (or neural networks) are computational models patterened after the biological processes of the brain, specifically neurons.

Neural networks allow for the modeling of complex patterns due to its ability to create deep architectures. (*Spoiler: More to come in deep learning talk.*)

Neural networks come in many learning paradigms:
- supervised 
- unsupervised
- reinforcement

---

## This is a neuron
![Image](./images/neuron.gif)
  
<div class='source'>
  Source: <a href='webspace.ship.edu'>Picture from webspace.ship.edu</a>
</div>

---
## Modeling A Neuron
![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

---
## Add some dendrites
![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 


---
## And the axon/axon terminal

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 


---
## Add some math!

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5.png) 

---
## Nodes forming a network

![Image](./images/neural_network_1.png)
  
<div class='source'>
  Source: <a href='www.astroml.org'>Picture from www.astroml.org</a>
</div>

---
## Neuron Activation Functions
<style>
p {
  margin-top: 1.0em !important;
}
.MathJax_Display {
  margin: 0em 0em 1em !important;
}

.math span{
  font-size: 100% !important;
  color: #000000;
}

</style>
1. Linear Neurons: 
$$y = b + \sum_{i} x_{i} w_{i}$$

2. Binary Threshold Neurons: 
$$z = \sum x_{i} w_{i}\\
y =
\begin{cases}
    1   & z \geq \theta \\
    0              & \text{otherwise}
\end{cases}$$

3. Rectified Linear Neurons:
$$y =
\begin{cases}
    z   & z \geq \theta \\
    0              & \text{otherwise}
\end{cases}$$

---&twocol w1:50% w2:50%
## More on Binary Threshold Neurons

*** left

Binary threshold is the most common choice for modeling individual neuron nodes.
- A sigmoid distribution is often used to model the activation function.  This is the same function used in logistic regression.
- A binary threshold neuron passes a 0 or 1 value to the next layer depending on whether the activation threshold had been met.


*** right

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 


---
## Back to our XNOR problem

```r
inputs <- data.frame(A=sample(c(0,1), 100,replace=TRUE),B=sample(c(0,1), 100, replace=TRUE))
inputs$XNOR <- ifelse(inputs$A == inputs$B, 1, 0)
net.xnor <- neuralnet(XNOR~A+B, data=inputs, hidden=2, rep=10)
```

![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-7.png) 


---
## Application of Neural Nets

Neural Networks excels at recognizing complex patterns and adapting to non-linear relationships.

- Handwriting Analysis 
  - [Yann Lecun's LeNet-5](http://yann.lecun.com/exdb/lenet/index.html)
  - [Kaggle Digit Recognizer Contest](http://www.kaggle.com/c/digit-recognizer)
- Self-Driving Vehicles 
  - [ALVINN](http://ftp.utcluj.ro/pub/docs/imaging/Autonomous_driving/Articole%20sortate/CThorpe/ALVINN%20Project%20Home%20Page.htm)
  - [David Singleton NNRCAR](http://blog.davidsingleton.org/nnrccar/)
- Image/Voice Recognition (Deep Learning)
- Lots more!

---
## Additional Resources

- Ryan Harris's Video on Back Propagation [Part1](https://www.youtube.com/watch?v=aVId8KMsdUU) and [Part2](https://www.youtube.com/watch?v=zpykfC4VnpM)
- Wikipedia Rocks [Artificial Neural Network](http://en.wikipedia.org/wiki/Artificial_neural_network)
- Geoffrey Hinton's Class on [Neural Networks for Machine Learning](https://class.coursera.org/neuralnets-2012-001)


