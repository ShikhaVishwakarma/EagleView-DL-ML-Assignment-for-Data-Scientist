# EagleView-DL-ML-Assignment-for-Data-Scientist
Explanation: After importing required libraries, I created a dataframe of the image dataset with the labels on them namely, 'Person' and 'Car'. I created three sets of the data as train, validation and test then trained the convolutional neural network which is the best model for image classification of such types of projects. It has two layers of Conv2D which has relu activation function 2 of MaxPoollayer, 1 Global average pooling layer and 2 Dense layers. In the output layer sigmoid activation is used because this is a binary classification problem and the sigmoid function gives 1 or 0 as an output. The model gained 49.33% of accuracy and 0.69 of loss. In the end precision, recall, f1 score along with the confusion matrix has been calculated. I tested the model with a different image downloaded from the internet and the model accurately classifies it.
