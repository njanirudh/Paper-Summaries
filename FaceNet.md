__Title__		: FaceNet: A Unified Embedding for Face Recognition and Clustering </br>
__Author__ 	: Florian Schroff, Dmitry Kalenichenko, James Philbin </br>
__ArXiv__		: https://arxiv.org/abs/1503.03832 </br>

------

### Abstract

Despite significant recent advances in the field of face recognition [10, 14, 15, 17], implementing face verification and recognition efficiently at scale presents serious challenges to current approaches. In this paper we present a system, called FaceNet, that directly learns a mapping from face images to a compact Euclidean space where distances directly correspond to a measure of face similarity. Once this space has been produced, tasks such as face recognition, verification and clustering can be easily implemented using standard techniques with FaceNet embeddings as feature vectors. 

Our method uses a deep convolutional network trained to directly optimize the embedding itself, rather than an intermediate bottleneck layer as in previous deep learning approaches. To train, we use triplets of roughly aligned matching / non-matching face patches generated using a novel online triplet mining method. The benefit of our approach is much greater representational efficiency: we achieve state-of-the-art face recognition performance using only 128-bytes per face.
On the widely used Labeled Faces in the Wild (LFW) dataset, our system achieves a new record accuracy of 99.63%. On YouTube Faces DB it achieves 95.12%. Our
system cuts the error rate in comparison to the best published result [15] by 30% on both datasets.

We also introduce the concept of harmonic embeddings, and a harmonic triplet loss, which describe different versions of face embeddings (produced by different networks) that are compatible to each other and allow for direct comparison between each other.

### Keywords
Triplet-loss , face embedding , harmonic embedding

------ 

## Summary

### Introduction

**Goal of the paper**    
A unified system is given for face verification , recognition and clustering.
Use of a 128 float  pose and illumination invariant feature vector or embedding in the euclidean space.
* Face Verification : Same faces of the person gives feature vectors that have a very close L2 distance between them. 
* Face recognition : Face recognition becomes a clustering task in the embedding space
	
**Previous work**    
* Previous use of deep learning made use of an bottleneck layer to represent face as an embedding of  1000s  dimension  vector.
* Some other techniques use PCA to reduce the dimensionality of the embedding for comparison.

**Method**
* This method makes use of inception style CNN to get an embedding of each face.
* The thumbnails of the face image are the tight crop of the face area with only scaling and translation done on them.
	
**Triplet Loss**
Triplet loss  makes use of two matching face thumbnails and a non-matching thumbnail. The loss function tries to reduce the distance between the matching pair while increasing the separation between the the non-matching pair of images.

**Triplet Selection**
* Selection of triplets is done such that samples are hard-positive or hard-negative .
* Hardest negative can lead to local minima early in the training and a collapse model in a few cases
* Use of semi-hard negatives help to improve the convergence speed while at the same time reach nearer to the global minimum.

**Deep Convolutional Network**
* Training is done using SGD (Stochastic gradient descent) with Backpropagation and AdaGrad
* The training is done on two networks :
    - Zeiler&Fergus architecture with model depth of 22 and 140 million parameters
    - GoogLeNet style inception model with 6.6 to 7.5 million parameters.

**Experiment**
* Study of the following cases are done :
    - Quality of the jpeg image : The validation rate of model improves with the JPEG quality upto a certain threshold.

    - Embedding dimensionality : The dimension of the embedding increases from 64 to 128,256 and then gradually starts to decrease at 512 dimensions. 

    - No. of images in the training data set 



**Results classification accuracy** :
   - LFW(Labelled faces in the wild) dataset : 98.87% 0.15
   - Youtube Faces DB : 95.12%  .39
On clustering tasks the model was able to work on a wide varieties of face images and is invariant to pose , lighting and also age.

**Conclusion**

* The model can be extended further to improve the overall accuracy.
* Training networks to run on smaller systems like mobile phones.
* There is need for improving the training efficiency.

---

## Notes 

* Harmonic embedding is a set of embedding that we get from different models but are compatible to each other. This helps to improve future upgrades and transitions to a newer model

* To make the embeddings compatible with different models , harmonic-triplet loss and the generated triplets must be compatible with each other

## Open research questions

* Better understanding of the error cases.
* Making the model more compact for embedded and mobile use cases.
* Methods to reduce the training times.

