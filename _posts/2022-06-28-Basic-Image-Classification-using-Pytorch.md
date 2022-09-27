## Basic Image Classification using Pytorch/ Pytorch Lightning

In the first three weeks of my internship, I learned and created Convolutional Neural Network (CNN) models with no prior deep learning background. 
Using the **MNIST and CIFAR10 datasets**, I created 2 CNN models:
   - large weight 
   - linear models 
 
 Google Colab Notebook was used to utilize the available GPU provided to train CNN with Pytorch Lightning, running several times faster than CPU. 
 Pytorch Lightning served as a simplicity for me to run the scripts and fit any use case with flexibility.
 Afterwhich, the notebooks were converted to Python scripts using Vim and uploaded to my repository on Github.
 In my scripts, I have also tried the argparse module available in Python for users to choose between the different types of models and datasets they want to train. 

Overall, these are my learning points from this project: 
  - Using MNIST (handwritten digits) and CIFAR10 (colour images) Datasets 
  - Increasing the weights of CNN models (small, middle, large) by increasing convolutional layers 
  - Training with different optimizers (Adam, SGD) and lr to find the best fit model
  - Difference between Pytorch and Pytorch Lightning 
  - Added argsparse to suit user's preference 

Github Repository: https://github.com/claudiamohh/pytorch-image-classifier
