__Title__		:  One pixel attack for fooling deep neural networks
__Author__ 	:  Jiawei Su, Danilo Vasconcellos Vargas, Sakurai Kouichi 
__ArXiv__		: https://arxiv.org/abs/1710.08864

------

### Abstract

Recent research has revealed that the output of Deep Neural Networks (DNN) can be easily altered by adding relatively small perturbations to the input vector. In this paper, we analyze an attack in an extremely limited scenario where only one pixel can be modified. For that we propose a novel method for generating one-pixel adversarial perturbations based on differential evolution. It requires less adversarial information and can fool more types of networks. The results show that 68.36% of the natural images in CIFAR10 test dataset and 41.22% of the ImageNet (ILSVRC 2012) validation images can be perturbed to at least one target class by modifying just one pixel with 73.22% and 5.52% confidence on average. Thus, the proposed attack explores a different take on adversarial machine learning in an extreme limited scenario, showing that current DNNs are also vulnerable to such low dimension attacks.


### Keywords
One pixel attack , adversarial examples , differential evolution

------

### Summary

##### Introduction


##### Conclusion 


-----
##### Notes 

* Data points may be located near the decision boundaries
* The data points are moved in small steps and the change in the class probabilities are observed.


##### Open research questions

[1] Effect of a larger set of initial candidate solutions to finding the adversarial image.
[2] Generate better adversarial examples by having more iterations. 
