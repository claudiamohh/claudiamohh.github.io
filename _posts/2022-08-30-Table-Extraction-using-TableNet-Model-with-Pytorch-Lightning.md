## Table Extraction using TableNet Model with Pytorch Lightning

This project is a semantic segmentation task which labels each pixel of an image with a corresponding class of what is being represented. One popular approach for semantic segmentation models is to follow an encoder/decoder structure, which explains the reason of using TableNet model. 

---
### Dataset
 The Marmot dataset is used to train the TableNet model. The dataset consists of: images, table_mask, column_mask. 
 
 Examples of dataset: 
 ![Screenshot 2022-09-28 005120](https://user-images.githubusercontent.com/107597583/192587968-0a756041-40f2-46de-be96-4ef0390f90f0.png)
 
  If a table/column exists, it will be covered with a white area in the table_mask/column_mask. Hence, the pixels in the white area will be labeled '255' (table/column exists) while the pixels in the black area will be labeled '0' (no table/column). 

 To have a better understanding of the Marmot dataset, an exploratory data analysis (EDA) of the dataset was created.
 The [EDA notebook](https://github.com/claudiamohh/lightning-tablenet/blob/main/notebooks/Marmot_EDA.ipynb) was essential as it allowed me to understand more details of the dataset.
 
 There were several errors in the dataset: 
  1. 509 different images in the dataset whereas there are 510 column mask files and 510 table masks files
  2. table_mask displays more than one table when the image has only one table, shown below
  
  ![image](https://user-images.githubusercontent.com/107597583/192589249-1ce53acd-7abc-4414-a5cc-bfefaafa2f3e.png)

 ---
### Experimental Results and Discussion 
  
 As the baseline model was not learning, I tried to fine-tune the model with different optimizers, types of backbone models and learning rate. The different optimizers used are: (1) Adam optimizer and (2) Stochastic Gradient Descent (SGD) optimizer. TableNet models trained with Adam opimizer had an instable training loss; spiking up and down while models trained with SGD optimizer were not learning (eg. highest validation loss when trained with SGD optimizer, refer to row-21 below). After training with different parameters, such as, low learning rates (i.e, 5e-3), using VGG-19 with batch normalisation, gradient clipping and weight decay, I found the model with gradient clipping to be the best. It was also able to stabilize the model training process. Below are the results of the models with different parameters, each trained for 3 times get the lowest validation loss.  
 
| Model | No. of epochs | Validation Loss | Binary mean IOU for table | Binary mean IOU for column | 
|-------|---------------|-----------------|---------------------------|----------------------------|
|1. tablenet_baseline_adam_1| 1 | 0.384 | 0.740 | 0.652 |
|2. tablenet_baseline_adam-2| 4 | 0.361 | 0.750 | 0.650 | 
|3. tablenet_baseline_adam_3| 28 | 0.298 | 0.807 | 0.697|
|4. tablenet_baseline_adam_gradclipping_1| 56 | **0.212** | 0.753 | 0.689|
|5. tablenet_baseline_adam_gradclipping_2| 25 | 0.225 | 0.682 | 0.709|
|6. tablenet_baseline_adam_gradclipping_3| 24 | 0.220 | 0.756 | **0.717**|
|7. tablenet_baseline_adam_gradclipping_weightdecay_1| 9 | 0.321 | 0.136 | 0.112|
|8. tablenet_baseline_adam_gradclipping_weightdecay_2| 11 | 0.299 | 0.136 | 0.111|
|9. tablenet_baseline_adam_gradclipping_weightdecay_3| 6 | 0.342 | 0.136 | 0.113|
|10. tablenet_baseline_adam_lr_5e-5_1|19|0.286| **0.812**| 0.707
|11. tablenet_baseline_adam_lr_5e-5_2|20|0.266| 0.572| 0.673
|12. tablenet_baseline_adam_lr_5e-5_3|26|0.281|0.796| 0.715
|13. tablenet_baseline_adam_transposed_1|0|0.456| 0.649| 0.651|
|14. tablenet_baseline_adam_vggbn_lowlr_1|19|0.285|0.136|0.111
|15. tablenet_baseline_adam_vggbn_lowlr_2|39|0.285|0.136|0.112
|16. tablenet_baseline_adam_vggbn_lowlr_3|30|0.288|0.136|0.112
|17. tablenet_baseline_sgd_onecycelr_1|44|0.488|0.226| 0.279|
|18. tablenet_baseline_sgd_onecycelr_2|45|0.583|0.592|0.497|
|19. tablenet_baseline_sgd_onecycelr_3|52|0.511|0.585|0.302
|20. tablenet_baseline_sgd_onecycelr_lowlr_1|55|0.459|0.252| 0.242
|21. tablenet_baseline_sgd_onecycelr_lowlr_2|91|0.804|0.161|0.233 |
|22. tablenet_baseline_sgd_onecycelr_lowlr_3|37|0.648|0.177| 0.137| 

`tablenet_baseline_adam_gradclipping_1` has the lowest validation loss of 0.212 and decent values of binary mean IOU for table and column of 0.753 and 0.689 respectively. This model checkpoint is available for users to download in my Github Repository [lightning-tablenet](https://github.com/claudiamohh/lightning-tablenet) if they do not want to train the model.

---

After training the model with gradient clipping, OCR tesseract was used to predict and recognize content of the columns. And lastly, a gradio demo is created where users are able to drag/upload an image and the output will return a dataframe of the contents in the table. 
![Screenshot 2022-08-24 173202](https://user-images.githubusercontent.com/107597583/186386131-392d7866-91fe-4bb9-9655-ac260f1f4d29.png)

--- 
Learning points from this project: 
- Learned to create an EDA on the Marmot Dataset
- Learned to create model checkpoints 
- Learned to read TensorBoard graphs
- Learned to fix parameters when model is not learning/training loss increases
- Learned to demo using Gradio interface
- Learned to have the best coding practice (e.g., writing docstring, descriptive variable names)
