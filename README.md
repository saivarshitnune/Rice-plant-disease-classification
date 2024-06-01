# Automated Classification of Rice Plant Diseases Using AI

Rice plants are vulnerable to several diseases, such as Bacterial Blight (BB), Brown Spot (BS), and Leaf Smut (LS), which significantly impact crop yield and quality. Effective diagnosis and management of these diseases are crucial for ensuring food security and the livelihood of farmers. The Rice Life Disease Dataset provides comprehensive data on these diseases, encompassing various attributes and parameters. The objective is to develop a machine learning model that can accurately classify the type of disease affecting the rice plants based on the provided dataset. This model will help agronomists and farmers in early detection and precise management of rice plant diseases.

![Rice plant](https://github.com/saivarshitnune/Rice-plant-disease-classification/assets/121888709/6e5bfb8f-5bf8-4e3d-831b-341c64bcb5e4)


# About Data :-
The Rice Life Disease Dataset is an extensive collection of data focused on three major diseases that affect rice plants: Bacterial Blight (BB), Brown Spot (BS), and Leaf Smut (LS). The dataset has been curated to assist researchers, agronomists, and machine learning practitioners in understanding, diagnosing, and potentially predicting the occurrence of these diseases, based on various attributes and parameters.

 Dataset contains images of the Unhealthy Rice Plant Leaves.

1. Disease Type: This categorizes the observation into one of the three diseases: Bacterial Blight (BB), Brown Spot (BS), or Leaf Smut (LS).

2. Leaf Images: High-resolution images of rice leaves exhibiting symptoms of the specified disease. This aids in visual diagnosis and machine learning-based image recognition tasks.

3. Symptom Description: Textual description outlining the major symptoms visible on the leaf, offering a more detailed understanding of the disease's progression and manifestation.

4. Environmental Parameters: Data on temperature, humidity, and other weather conditions at the time of observation. This can help in understanding the environmental triggers for each disease.

The Rice Life Disease Dataset is a comprehensive collection of 4684 high resolution images divided into three classes

    Bacterial Blight (BB) - 1604 images

    Brown Spot (BS) - 1620 images

    Leaf Smut (LS) - 1460 images 

![Data sample](https://github.com/saivarshitnune/Rice-plant-disease-classification/assets/121888709/5e0b9773-69b5-4ae2-9739-23f921a5a54b)

# Approach 
1. Preprocess and analyze the dataset to understand the key features influencing disease classification.
2. Develop a deep learning model to classify the rice plant disease effectively.
3. Validate the model's performance using appropriate metrics and ensure its robustness and reliability in real-world scenarios.

# Data Understanding 
On detailed scrutiny of the data we found our data has below distribution of each class in train,test and valid (0.7,0.15,0.15) respectively.

![Table](https://github.com/saivarshitnune/Rice-plant-disease-classification/assets/121888709/236412e5-6ab1-44bd-b6d5-165fbf6877a9)



    



Our classification is mainly influenced by brown colour pigmentation on the leaf. It is observed that
1. For the images which is having Bacterial Blight has long continuous brown pigmentation at the edges of the leaf
2. For the images which is having Brown Spot has multiple small brown dots on the leaf at different locations.
3. For the images which is having Leaf Smut has multiple elliptical brown pigmentation on the leaf at different locations.

So brown colour pigmentation is common in all the disease types. Our selected model and loss function should be complex enough to classify based on its shape (In a human understading method)

# Model Selection :-
 As per our understanding the model should be able to learn the subtle differences in the complex visual features , which a deep nueral network can achieve.
 Here we are selecting ResNet50 as our model architecture because of its residual connections to tackle vanishing gradient problems in deeper networks.
 Please refer https://arxiv.org/pdf/1512.03385 for ResNet understanding.

# Training
  Frame work : Pytorch
  
  Model : ResNet50
  
  Base weights : ImageNet 
  
  Loss function : CategoricalCrossentropy
  
  Optimizer : Adam
  
  Learningrate : 0.001
  
  Number of epochs : 50
  
  Call backs - EarlyStopping , ModelCheckpoints.
  
# Performance evaluation metrics
 1. Confusion matrix :
    
      ![cm](https://github.com/saivarshitnune/Rice-plant-disease-classification/assets/121888709/77c1363f-997a-4307-99c4-9ffd642e45c9)
    
      There are no missclassifications and model has perfectly classified each sample to respective class.
    
2. Classification Report :

   ![CR](https://github.com/saivarshitnune/Rice-plant-disease-classification/assets/121888709/fd354225-c51a-435f-8f2e-0e23443f00a4)
   
   Achieved an
   
   Test Accuracy of 100 %
   
   100% Recall
    
   100% precision
   
   100% F1 score

 # Conclusion 
 This project showcases the potential of deep learning models, particularly ResNet50, in addressing agricultural challenges. By accurately diagnosing and classifying rice plant diseases, this model contributes to better crop health and yield, ultimately supporting sustainable agriculture practices and can be improved by training with more diversified and more number of samples for robust disease classification.

 # Try It out 
  1. Open test.ipynb
  2. Connect to google colab runtime
  3. Run the cells that contain importing the required modules and downloading the model weights and loading the model 
  4. Select the image from sample images and run the test cell and see the result






     
