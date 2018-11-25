__Title__		:  Intriguing properties of neural networks <br/>
__Author__ 	:  Christian Szegedy, Wojciech Zaremba et al. <br/>
__ArXiv__		: https://arxiv.org/abs/1312.6199 <br/>

------

### Abstract

Deep neural networks are highly expressive models that have recently achieved state of the art performance on speech and visual recognition tasks. While their expressiveness is the reason they succeed, it also causes them to learn uninterpretable solutions that could have counter-intuitive properties. In this paper we report two such properties.

First, we find that there is no distinction between individual high level units and random linear combinations of high level units, according to various methods of unit analysis. It suggests that it is the space, rather than the individual units, that contains the semantic information in the high layers of neural networks. 

Second, we find that deep neural networks learn input-output mappings that are fairly discontinuous to a significant extent. We can cause the network to misclassify an image by applying a certain hardly perceptible perturbation, which is found by maximizing the network’s prediction error. In addition, the specific nature of these perturbations is not a random artifact of learning: the same perturbation can cause a different network, that was trained on a different subset of the dataset, to misclassify the same input.

### Keywords
Adversarial example ,  Perturbations 

------

### Summary

##### Introduction 

* Explain two properties of  neural network that cause it to misclassify images and cause  difficulty to get solid understanding of network.
1. Theoretical understanding  of the individual high level unit of a network and a combination of these units or layers.
2. Understanding the continuity of input - output mapping space and the stability of the output wrt. the input.

* Performing a few experiments on different networks and architectures
1. MNIST dataset - Autoencoder , Fully Connected net
2. ImageNet - “AlexNet”
3. 10M youtube images - “QuocNet”  

##### Understanding individual units of the Network 

* Previous work used individual images to maximize the activation value of each feature unit.
Similar experiment was done by the authors on the MNIST data set.

* The interpretation of the results are as following ;
1. Random direction vector (V)  gives rise to similarly interpretable semantic properties.
2. Each feature unit is able to generate invariance on a particular subset of input   distribution.
![Feature](images/Selection_001.png?raw=true "Features of Individual units")

##### Blind spots in the neural network

* Output layers are highly non-linear and are able to give a nonlinear generalization over the input space.
* It is possible for the output layers to give non-significant probabilities to regions of the input space that contain no training examples in their vicinity. Ie. It is possible to obtain probability of the different viewpoints of the object without training.
* Deep learning kernel methods can't be assumed to have smooth decision boundaries. 
* Using optimization techniques, small changes to the image can lead to very large deviations in the output
* __“Adversarial examples”__ represent pockets or holes in the input-space which are difficult to find simply moving around the input images.


##### Experimental Results
* Adversarial examples that are indistinguishable from the actual image can be created for all networks.
1. Cross model generalization : Adversarial images created for one network can affect the other networks also.
2. Cross training generalization 

![Feature](images/Selection_003.png?raw=true "Features of Individual units")

##### Conclusion 
* Neural network have a counter intuitive properties wrt. the working of the individual units and discontinuities.
* Occurance of the adversarial examples and its properties. 

-----
##### Notes 

* Feeding adversarial examples during the model training can improve the generalization of the model.
* The adversarial examples on the higher layers are more effective than those of input and lower layers.
* Adversarial examples affect models trained with different hyper parameters.
* According to the the test conducted , autoencoders are more resilient to the adversarial examples.
* Deep learning networks which are trained from purely supervised training are unstable to a few particular types of perturbations. Small addition of perturbations to the input leads to large perturbations at the output of the last layers.

##### Open research questions

[1] Comparing the effects of adversarial examples on lower layers to that of the higher layers.<br/>
[2] Dependence of the adversarial attacks on training data set of the model.<br/>
[3] Why the adversarial examples generalize across different hyperparameters or training sets.<br/>
[4] How often do adversarial example occur?<br/>

