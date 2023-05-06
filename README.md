# Project-2-Part1:Toxic Comment Classification
# Introduction

In this part, we are going to explore basic text processing using the toxic comment text classification dataset. Although the machine learning and text processing techniques employed are not sophisticated, our primary objective is to convert the comment text column into a sparse vector representation that can be utilized by a classification algorithm within the Spark ML library.

# Data Description

The Toxic Comment Text Classification dataset is a large dataset originally released by Jigsaw and Google. The data is formatted as a csv file, with each row representing a unique comment. The columns in the dataset include id, comment\_text, and other binary labels (0 or 1) indicating whether the comment falls into the respective toxicity category. 

# Model Explanation and Evaluation

The chosen model for this task is Logistic Regression, which is implemented using the PySpark 'LogisticRegression' class. 
The model is trained separately for each label column in the 'out\_cols' list, excluding the 'id' and 'comment\_text' columns. The regularization parameter (REG) is set to 0.1 to prevent overfitting. For each label, the model is fit on the training dataset with TF-IDF features and then used to make predictions on the test dataset. The probability of a comment being classified as toxic is extracted and added to the 'test\_res' DataFrame. This process is repeated for all labels in the 'out\_cols' list.

We got the first 20 rows with the comment ids and the predicted probabilities for each class as output. 
