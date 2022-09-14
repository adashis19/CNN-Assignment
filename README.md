# Melanoma Detection Assignment
Problem statement: To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.


## Steps:
1. Data Reading/Data Understanding → Defining the path for train and test images 
2. Dataset Creation→ Create train & validation dataset from the train directory with a batch size of 32. Also, make sure you resize your images to 180*180.
3. Dataset visualisation → Create a code to visualize one instance of all the nine classes present in the dataset 
4. Model Building & training:
4.1 Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
4.2 Choose an appropriate optimiser and loss function for model training
4.3 Train the model for ~20 epochs
4.4. Write your findings after the model fit. You must check if there is any evidence of model overfit or underfit.
5. Chose an appropriate data augmentation strategy to resolve underfitting/overfitting 
6. Model Building & training on the augmented data :
6.1 Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel values between (0,1).
6.2 Choose an appropriate optimiser and loss function for model training
6.3 Train the model for ~20 epochs
6.4 Write your findings after the model fit, see if the earlier issue is resolved or not?
7. Class distribution: Examine the current class distribution in the training dataset 
- Which class has the least number of samples?
- Which classes dominate the data in terms of the proportionate number of samples?
8. Handling class imbalances: Rectify class imbalances present in the training dataset with Augmentor library.
9. Model Building & training on the rectified class imbalance data :
10. Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
10.1 Choose an appropriate optimiser and loss function for model training
10.2 Train the model for ~30 epochs
10.3 Write your findings after the model fit, see if the issues are resolved or not?

## Conclusions

1.   We loaded the train dataset to google drive and mounted the drive on google collab workspace
2.   Visualized one example of each of the classes
3. Built model (Model 1) basis 3 layers of convolutions and added max pooling at the end of those 3 layers. The model was flattened at the end before using softmax function to classify.
4. The above model produced an overfitting model with **Training Set accuracy of 86% and Validation Set 48%.**
5. To resolve the above problem, we increased the sample size by augmenting the date.
6. We ran the model with augmented data (Model 2), which solved overfiiting problem but reduced **training accuracy to 51%.**
7. Thereafter we looked at class imbalance and added 500 samples to each of the classes.
8. Model (No. 3) was run with increased sample size and had the result of **Training accuracy - 95% and validation accuracy - 75%**
9. Since the above was overfitting, we ran 3 new models as follows:
- **Model 4** (Experiment - I: Using dropouts after conv and FC layers)
  - **Training Accuracy - 82%**
  - **Validation Accuracy - 71%**
- Model 5 (Experiment - II: Remove the dropouts after the convolutional layers (but retain them in the FC layer). Also, use batch normalization after every convolutional layer)
  - Training Accuracy - 93%
  - Validation Accuracy - 64%
- Model 6 (Experiment - III: Use batch normalization and dropouts after every convolutional layer. Also, retain the dropouts in the FC layer)
  - Training Accuracy - 93%
  - Validation Accuracy - 50%

**Final Result:**

**We Will keep Model 4** as the best model since it's not an overfitting model thought it can be improved to improve performance on validation score using more apporaches, but unfortunately ran out of GPU Usage in google collab.

