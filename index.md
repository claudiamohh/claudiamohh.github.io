This blog includes an internship summary in Handshakes as a Machine Learning Intern. 
I was involved in 3 projects during my time there, and I will breifly talk more about these projects below. 

### 3 Machine Learning Projects: 
  1. Image Classification with Pytorch / Pytorch Lightning
     
      This project serves as a gentle introduction to image classification task using deep learning models with Pytorch and Pytorch Lightning. It includes training of Linear models and Convolutional neural network (CNN) models to classify images of handwritten digits (i.e., MNIST dataset) and images of objects (i.e., CIFAR10 dataset), like airplanes, cars, bird and etc. Github repository: [pytorch-image-classifier](https://github.com/claudiamohh/pytorch-image-classifier)

  2. Table Extraction using TableNet Model with Pytorch Lightning

      This project is to implement the TableNet model, a novel deep learning model trained on dual tasks of table detection and structure recognition in an end-to-end fashion, to extract tables from images. It uses [VGG-19 pretrained model](https://arxiv.org/abs/1409.1556) as the encoder to extract features from images and outputs table region and column region masks from table decoder and column decoder, respectively. More details on the training scripts, experimental results, best model checkpoint and demo script can be found in my Github repsitory: [lightning-tablenet](https://github.com/claudiamohh/lightning-tablenet).
      
  3. Annotation of Table Structure Dataset for microsoft/table-transformer Model
     
     The last project involves the annotations of PDF files using [Prodigy](https://prodi.gy/) to annotate different table components (e.g., tables, rows, columns, etc.), to build a table structure dataset for training the table-transformer model from Microsoft. Unittests were also written to test and verify the converted xml annotation format. Complicated cases with unusual table format are documented and can be found here: [Handshakes Internal Ticket](https://handshakesbydc.atlassian.net/browse/AI-335).


### Learning Experiences In Handshakes: 
 - Different types of image classification tasks: Image Classification task and Semantic Segmentation task
 - Hands-on experience with PyTorch and PyTorch Lightning
 - Differences between Toy Dataset (eg. MNIST, CIFAR10) vs Real Word Dataset (i.e., Marmot, PDF files)
 - Using Gradio to demo TableNet model 
 - Familarize with python scripting, github branching concept and submit github PR to work with other developer
 - Best practice of: 
     - Writing docstring 
     - Descriptive variable names 
     - Arranging directory 
     - Naming of branches 
     - Clear Git commit messages 
     - writing unittests
 - Productivity tools (eg. vim, tmux) 

