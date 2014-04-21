---
title       : Neural Networks
subtitle    : A really brief firehosing
author      : Tommy Shen
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
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
![Image](./images/neuron.gif "webspace.ship.edu")

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
![Image](./images/neural_network_1.png "www.astroml.org")

---
## Back to our XNOR problem

```r
inputs <- data.frame(A=sample(c(0,1), 100,replace=TRUE),B=sample(c(0,1), 100, replace=TRUE))
inputs$XNOR <- ifelse(inputs$A == inputs$B, 1, 0)
net.xnor <- neuralnet(XNOR~A+B, data=inputs, hidden=2, rep=10)
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 


---
