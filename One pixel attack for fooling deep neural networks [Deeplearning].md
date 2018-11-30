## **Keywords**

One pixel attack , adversarial examples , differential evolution , targeted and non-targeted attack

---


## ** Summary**

1.  **Introduction**
    1.  **Basics**
        1.  Deep learning methods are better than the traditional image processing techniques in most of the cases in computer vision domain.
        1.  "Adversarial examples" are specifically modified images with imperceptible perturbations  that are classified wrong by the network.
    1.  **Goals of the paper**
        1.  In most of the older techniques excessive modifications are made on the images and it may become perceivable to the human eyes. The authors of the paper suggest a method to create adversarial examples by changing only one , three or five pixels of the image.
        1.  Generating examples under constrained conditions can help in _getting insights about the decision boundaries_ in the higher dimensional space.
    1.  **Previous Work**
        1.  Methods to create adversarial examples :
            1.  Gradient-based algorithms using backpropagation for obtaining gradient information 
            1.  "fast gradient sign" algorithm 
            1.  Greedy perturbation searching method
            1.  Jacobian matrix to build "Adversarial Saliency Map"
        1.  Understanding and visualizing the decision boundaries of the DNN input space.
        1.  Concept of "Universal perturbations" , a perturbation that when added to any natural image can generate adversarial samples with high effectiveness
1.  **Advantages of the new types of attack**
    1.  _Effectiveness_ : One pixel modification  with efficiency ranging from 60% - 75%.
    1.  _Semi-Black-Box attack _: Requires only black-box feedback (probability labels) , no gradient and network architecture required.
    1.  _Flexibility_ : Can generalize between different types of network architectures.
1.  **Methodology**
    1.  Finding the adversarial example as an optimization problem with constraints.** **
    1.  _Differential evolution_
        1.  _"Differential evolution" _, a general kind of  evolutionary algorithms , used to solve multimodal optimization problems.
        1.  Does Not make use of gradient information
        1.  Advantages of DE for generating adversarial images :
            1.  _Higher probability of finding the global optima_
            1.  _Requires less information from the target system_
            1.  _Simplicity_ : Independent of the classifier 
1.  **Results**
    1.  CIFAR-10 dataset was selected with 3 types of networks architectures , all  convolution  network  ,  Network  in  Network  and  VGG16 network . 500 random images were selected to create the perturbations and run both _targeted_ and_ non-targeted attack._
    1.  Adversarial examples were created with only one pixel change in some cases and with 3 and 5 pixel changes in other cases.
    1.  The attack was generalized over different architectures.
    1.  Some specific target-pair classes are more vulnerable to attack compared to the others.
    1.  Some classes are very difficult to perturb to other classes and some cannot be changed at all.
    1.  Robustness of the class against attack can be broken by using higher dimensional perturbations.
    
1.  **Conclusion**
    1.  Few pixels are enough to fool different types of  networks.
    1.  The properties of the targeted perturbation depends on its decision boundary.
    1.  Assumptions made that small changes addictive perturbation on the values of many dimensions will accumulate and cause huge change to the output , might not be necessary for explaining why natural images are sensitive to small perturbation.



---


## **Notes**



*   Location of data points near the decision boundaries might affect the robustness against perturbations.
    *   If the boundary shape is wide enough it is possible to have natural images far away from the boundary such that it is hard to craft adversarial images from it.  
    *   If the boundary shape is mostly long and thin with natural images close to the border, it is easy to craft adversarial images from them but hard to craft adversarial images to them.
*   The data points are moved in small steps and the change in the class probabilities are observed.

## **Open research questions**



1.  Effect of a larger set of initial candidate solutions( Training images) to finding the adversarial image?
1.  Generate better adversarial examples by having more iterations of Differential evolution?
1.  Why imbalances occur when creating perturbations?
