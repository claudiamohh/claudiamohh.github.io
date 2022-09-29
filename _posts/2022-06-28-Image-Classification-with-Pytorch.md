## Image Classification with Pytorch / Pytorch Lightning

In the first three weeks of my internship, I learned to train image classification models with Pytorch and Pytorch Lightning libraries with no prior deep learning background. I built linear models and Convolutional Neural Network (CNN) models to classify images with two different datasets. 

The first dataset, MNIST, is a handwritten digits dataset which consists of single digits between 0 to 9. MNIST has 70,000 handwritten digits and each digit in the dataset is a 28x28 grayscale image. 

Figure below contains sample images of the MNIST dataset.

![image](https://user-images.githubusercontent.com/107597583/192945073-410f9dc9-6b7d-4369-97d7-25d3f3fefbbd.png)

The second dataset, CIFAR10, is most widely used for image classification tasks. The dataset has 60,000 coloured images, with each sample as a 32x32 colour image. The images belong to one of the predefined classes: airplanes, cars, birds, cats, deer, dogs, frogs, horses, ships and trucks. 

Figure below are sample images of the CIFAR10 dataset. 

![image](https://user-images.githubusercontent.com/107597583/192946020-00254f23-e67f-4086-84da-58ae6c0ea74d.png)


   
 Similar to others, I prototyped my image classification models on Google Colab notebooks and trained my models with the free GPU provided. Firstly, I wrote all my model training codes with PyTorch, in order to have a solid fundamental understanding of the native PyTorch style. Subsequently, I wrote the codes again with PyTorch Lightning framework. By doing this, I had the hands-on experience in both frameworks and was able to see the benefits and differences of using them.
    
 Afterwhich, I converted all my models' training codes from Google Colab notebook to Python scripts, allowing users to train the models via command. In addition, I have added [argparse module](https://docs.python.org/3/library/argparse.html) to write user-friendly command-line interfaces which allow users to select different arguments to train their models. 

  For more information, please refer to my Github Repository: [Pytorch Image Classifier](https://github.com/claudiamohh/pytorch-image-classifier). 
  
 ---
Command to train the Linear model with MNIST dataset: 
```
$ python train.py --model linear --dataset mnist 

# with Pytorch Lightning
$ python lightning_train.py --model linear --dataset mnist
```

Command to train the CNN model with MNIST dataset: 
```
$ python train.py --model cnn --dataset mnist

# with Pytorch Lightning
$ python lightning_train.py --model cnn --dataset mnist
```
---

A more detailed explanation of Linear model is to firstly, flatten an input image to a 1D vector before passing it into the Linear model. A grayscale image of the MNIST dataset has a size of 28x28x1, resulting in a 1D vector of size 784. The vector input will pass through all layers in the linear model and lastly reach the final output layer, which predicts the class of the input image. Architecture of a linear model is illustrated and shown in the following figure: 

![image](https://user-images.githubusercontent.com/107597583/192959280-af5cc07d-dbb8-4fb0-a70b-78be90d1086a.png)


As for the CNN model, it takes in the original image without reshaping/flattening as the input. The image will then be processed and passed through a series of Convolutional layers, Pooling layers and transformed into a 1D vector at the end of the model for classification. The 1D vector represents decimal probabilites to each class in a multi-class problem, adding up to 1.0. The class of the highest probability score in the vector is the predicted class index. Architecture of a CNN model is illustrated and shown in the following figure: 

![image](https://user-images.githubusercontent.com/107597583/192958169-9371c62a-34a2-4a6c-b045-10844b9f8068.png)

---

Overall, these are my learning points from this project: 
  - Using MNIST (handwritten digits) and CIFAR10 (coloured images) datasets 
  - Increasing the weights of CNN models (small, middle, large) by increasing the number of convolutional layers 
  - Training with different optimizers (Adam, SGD) and learning rate to find the best fit model
  - Difference between Pytorch and Pytorch Lightning 
  - Added argsparse to suit user's preference 

