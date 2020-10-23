---
title: Arm fracture detection in X-rays based on improved deep convolutional neural network
category: Review
tag: Detection, Fracture
---


>  ## ** Goal ** 

This paper's goal is to propose a novel deep learning method to detect arm fracture in X-rays.


>  ## ** Contribution ** 

**1. New backbone network based on feature pyramid architecture**

**2. Image preprocessing procedure**

**3. Receptive field adjustment with anchor scale reduction and tiny ROIs expansion

>  ## ** Method ** 

#### ** Backbone network**
  FPN + Fast R-CNN +RPN with <u?Gaussian non-local attention module (refine integrated features)</u>
    Integration of features (Novel method)

#### ** Preprocessing **
  Noise removal --> Morphological method
  Brightening --> Cumulative distribution function
  
#### **






<a href="https://i.imgur.com/SFqgxvX"><img src="https://i.imgur.com/SFqgxvX.png"  title="source: imgur.com" /></a>

.

> **Top accuracy**

**1. AmoebaNet**

**2. NASNet**

**3. SENet**

**4. DPN**

**5. PolyNet**

.

> **Info. Density** (Less calculation)

**1. SqueezeNext**

**2. TinyDarkNet**

**3. SqueezeNet**

**4. MobileNet**

**5. ZynqNet**




And here are the ratings by overall NetScore proposed by this [paper](https://arxiv.org/abs/1806.05512) which rated 60 different deep CNNs for the ILSVRC 2012 dataset.

<a href="https://i.imgur.com/pq2bpe9"><img src="https://i.imgur.com/pq2bpe9.png" title="source: imgur.com" /></a>



> **NetScore** 


**1. SqueezeNext**

**2. CondenseNet**

**3. MobileNetv2**

**4. TinyDarkNet**

**5. MobileNetv1 (1.0-128)**

**6. MobileNetv1 (1.0-160)**

**7. ShuffleNet (x2)**

**8. ShuffleNet (1.5)**

**9. MobileNetv1(1.0-192)**

**10. ZynqNet**

**26. DenseNet-121 (k=32)**

**33. ResNet-50**


.

We should note that less computation does not mean faster testing time. But if accuracy is similar, models with less computation can be more beneficial. Also implementation on mobile phones would be much better. 

Also we should note that this post doesn’t mean that **SqueezeNext** is way better than ResNet. There should be further testing with other datasets.


Here is the link to [SqueezeNext]( https://arxiv.org/abs/1803.10615) which I will try to write a new post covering this network someday.
