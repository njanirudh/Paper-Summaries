
## **Keywords**

Progressive GAN , High resolution generator

---

## **Summary**

1.  **Introduction**
    1.  **Goal of the paper**
        1.  Generation of very high quality images using progressively increasing size of the generator and discriminator.
        1.  Improved training and stability of GANs.
        1.  New metric for evaluating GAN results.
        1.  A high quality version of CELEBA-HQ dataset.
    1. **Previous Research**
        1.  Generative methods help to produce new samples from higher-dimensional data distributions such as images .
        1.  The common approaches for generative methods are :
            1.  Autoregressive models : Produce sharp images and are slow to evaluate. eg PixelCNN
            1.  Variational Autoencoders : Easy to train but produces blurry images.
            1.  Generative Adversarial Neural Network : Produces sharp images at small resolutions but are highly unstable.
1.  **Method**
    1.  **Basic GAN architecture**
        1.  Gan consists of two major parts :
            1.  _Generator_ : Creates a sample image from latent code which look very close to the training images.
            1.  _Discriminator_: Discriminator is trained to assess how close the sample image looks to the training image.
        1.  To measure the overlap between the training and the generated distributions many methods are used like Jensen-Shannon divergence , least-squares divergence and Wasserstein Distance.
        1.  Larger resolution generations cause problems because it becomes difficult for both the training and the generated networks amplifying the gradient problem. Larger resolutions also require large memory and can cause problems.
        1.  A mechanism is also proposed to stop the generator from participating in escalation that causes mode collapse problem.

    1.  **Progressive growing of GANs**
        1.  The primary method for the GAN training is to start off from a low resolution image and add extra layers in each step of the training process.
        1.  Lower resolution images are more stable as they have very less class information and as the resolution of the image increases further smaller details and features are added to the image.
        1.  This leads to a smooth increase in the quality of image instead of the network learning lot of details in one single step.
    1.  **Mini-batch separation**
        1.  GANs tend to capture only a very small set of features from the image.
        1.  "Minibatch discrimination" is used to generate feature vector for each individual image along with one for the the mini batch of images also.
        
          ![alt_text](https://i.imgur.com/dHFl5OV.png "image_tooltip")
1.  **Conclusion**
    1.  Higher resolution images are able to be generated which are robust and efficient.
    1.  Improved quality of the generated images is given.
    1.  Reduced training time for a comparable result and output quality and resolution.



---



## **Notes**



*   Gradient Problem : At higher resolutions it becomes easier to tell the differences between the training and the testing images [1]. This is referred to as the gradient problem.
*   Mode Collapse : The generator is incapable of creating a large variety of samples and get stuck.


## **Open research questions**



1.  Improved methods for a true photorealism generation of images.
1.  Improved semantic sensibility and improved understanding of the dataset.

## **References**



1.  [https://blog.acolyer.org/2018/05/10/progressive-growing-of-gans-for-improved-quality-stability-and-variation/](https://blog.acolyer.org/2018/05/10/progressive-growing-of-gans-for-improved-quality-stability-and-variation/) 
1.  [https://medium.com/@jonathan_hui/gan-why-it-is-so-hard-to-train-generative-advisory-networks-819a86b3750b](https://medium.com/@jonathan_hui/gan-why-it-is-so-hard-to-train-generative-advisory-networks-819a86b3750b)
