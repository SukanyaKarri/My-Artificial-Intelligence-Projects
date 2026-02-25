Problem Statement

Problem statement: 

To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution which can evaluate images and alert the dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.
The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant. The data set contains the following diseases:

Actinic keratosis
Basal cell carcinoma
Dermatofibroma
Melanoma
Nevus
Pigmented benign keratosis
Seborrheic keratosis
Squamous cell carcinoma
Vascular lesion

Procedural Steps:

Data Reading

Data creation

Data Visualization

Model Building and Training - Model 1

        -Chose optimizer and loss function
        - Train for 20 epochs
        - Mention the findings to ensure if model is overfit or underfit
Chose an augmenter to resolve underfitting & overfitting

Model building on augmented data - Model 2
       - create a CNN model, to detect 9 classes present in dataset
        -chose optimizer and loss function for model training
       - Train model for 20 eopchs
       - Mention findings and ensure if issues mentioned are resolved or not. 
       - check for class distribution 
       - Handle class imbalances by checking the least number of samples and class domination
Rectify class imbalance
Model building & training on the rectified class imbalance data - Model 3
       - Create a CNN model that can accurately detect 9 classes present
       - Chose an optimizer and loss function for model training
       - Train the model for 30 epochs
       - Write your findings after the model fit 

Platform preferred - Google colab.








