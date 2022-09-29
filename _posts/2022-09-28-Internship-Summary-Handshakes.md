### Machine Learning Internship Summary In Handshakes
This article includes an internship summary in Handshakes as a Machine Learning Intern (June 2022 - Sep 2022).



For more details on each project, it can be found here:  
  - [Image Classification with Pytorch / Pytorch Lightning](https://claudiamohh.github.io/2022/06/28/Image-Classification-with-Pytorch.html)
  - [Table Extraction using TableNet Model with Pytorch Lightning](https://claudiamohh.github.io/2022/08/30/Table-Extraction-using-TableNet-Model-with-Pytorch-Lightning.html)
  - [Annotation of Table Structure Dataset for microsoft/table-transformer Model](https://claudiamohh.github.io/2022/09/23/Annotation-of-Table-Structure-Dataset-for-table-transformor-model.html)


---
### Overview of Machine Learning Projects done in Handshakes:
  1. Image Classification with Pytorch / Pytorch Lightning
     
      This project serves as a gentle introduction to image classification task using deep learning models with Pytorch and Pytorch Lightning. It includes training of Linear models and Convolutional neural network (CNN) models to classify images of handwritten digits (i.e., MNIST dataset) and images of objects (i.e., CIFAR10 dataset), like airplanes, cars, bird and etc. Github repository: [pytorch-image-classifier](https://github.com/claudiamohh/pytorch-image-classifier)



 2. Table Extraction using TableNet Model with Pytorch Lightning



     This project is to implement the [TableNet model](https://arxiv.org/abs/2001.01469), a novel deep learning model trained on dual tasks of table detection and structure recognition in an end-to-end fashion, to extract tables from images. It uses [VGG-19 pretrained model](https://arxiv.org/abs/1409.1556) as the encoder to extract features from images and outputs table region and column region masks from table decoder and column decoder, respectively. More details on the training scripts, experimental results, model checkpoint and demo script can be found in my Github repository: [lightning-tablenet](https://github.com/claudiamohh/lightning-tablenet).
      
  3. Annotation of Table Structure Dataset for microsoft/table-transformer Model
     
     The last project involves the annotations of PDF files using [Prodigy](https://prodi.gy/) to annotate different table components (e.g., tables, rows, columns, etc.), to build a table structure dataset for training the table-transformer model from Microsoft. Unittests were also written to test and verify the converted xml annotation format. Complicated cases with unusual table format are documented and can be found here: [Handshakes Internal Jira Ticket](https://handshakesbydc.atlassian.net/browse/AI-335).



### Learning Experiences In Handshakes:
- Different types of image classification tasks: Image Classification task and Semantic Segmentation task
- Hands-on experience with PyTorch and PyTorch Lightning
- Differences between Toy Dataset (eg. MNIST, CIFAR10) vs Real World Dataset (i.e., Marmot, PDF files)
- Using Gradio to demo TableNet model
- Familarize with python scripting, github branching concept and submitting Github Pull Requests to work with other developers
- Best practice of:
     - Writing docstring
     - Naming descriptive variable names
     - Proper structure of Python code and directory
     - Naming Git branches
     - Meaningful and concise Git commit messages
     - Code reusabilty and Scalability  
        - DRY: Dont Repeat Yourself
        - SRP: Single Responsibility Principle
     - Tests
- Able to understand and debug errors faster 
- Productivity tools (eg. vim, tmux)


### Conclusion
All in all, the main takeaways from this internship were time management skills and independence, and also finding out my strengths and weaknesses. I am greatly humbled and thankful to my coworkers at Handshakes for providing me the ability to develop professionally and welcoming me as part of the family during my time here.  This internship was definitely a fruitful experience and I was able to gain practical skills, work in a fantastic environment, and make connections that will last a lifetime.
