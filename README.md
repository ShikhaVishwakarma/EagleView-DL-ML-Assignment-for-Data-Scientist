# EagleView-DL-ML-Assignment-for-Data-Scientist
## Brief Explanation
After importing required libraries, I created a dataframe of the image dataset with the labels on them namely, 'Person' and 'Car'. I created three sets of the data as train, validation and test then trained the convolutional neural network which is the best model for image classification of such types of projects. It has two layers of Conv2D which has relu activation function 2 of MaxPoollayer, 1 Global average pooling layer and 2 Dense layers. In the output layer sigmoid activation is used because this is a binary classification problem and the sigmoid function gives 1 or 0 as an output. The model gained 49.33% of accuracy and 0.69 of loss. In the end precision, recall, f1 score along with the confusion matrix has been calculated. I tested the model with a different image downloaded from the internet and the model accurately classifies it.

## Getting Started
From the given dataset I partitioned it in two categories- Cars and Person having 1117, 1122 in each. I am going to be using a keras convolutional neural network and for preprocessing the data I will use numpy, pandas, path object from pathlib and os.path then I am using confusion metric from seaborn. For train and test split I am using train test split function from sklearn and make the model with tensorflow.

## Construct a dataframe
I am creating a dataframe that contains one column with the lable of each image and such dataframe in essential if I am going to use flow from dataframe function from keras' image data generator. Flow from diractory is a function that automatically pulls images from the directories without loading all of them into memory at once. When using flow from direcories it's best to have train test split beforhand already within the direcories so I am using flow from dataframe which allows to manipulate which image we want to use. I am going to take the imagedir which is actually a path object and use the glob function on it and the glob allows you to specify a glob expression to search for files within the folder so we are looking for anything followed by a jpg file withing the current folder now it is a generator object.

## Creating the model
Now I split the dataframe in train and test with 70% of train size and keep the shuffle true. I load the image data so I am not going to load it into memory yet but specify how it will be loaded into memory at the time of training and for that I use generator tf.keras.preprocessing image data generator it allows us to load in only a batch of images at a time, perform the training on them and then recycle the memory so we don't run out. For preprocessing, I rescale the images by a factor of 1 over 255 which has the effect of scaling the pixel intensity values from its original scale of 0 to 255 down to 0 to 1. Last thing I want to put is the validation split of 20% of all the data. SO I am using 20 percent to validation and the other 80 percent training. 
I am going to do like a typical two hidden layer dense neural network. Since it's a binary classification task so sigmoid will give it the effect of being between zero and one so I'll output a single probability estimate for the positive. Now I'll create the model with tf.keras.model. will give it an atom optimizer and for loss we'll use binary cross entropy and for metrics and i'll just use accuracy to estimate the accuracy of the model. 

Now, I'll fit model.fit and then pass in train images and validation images. I specify the number of epochs we don't have to say the batch size since we declared that in the generators so it's trained for 100 epochs and i'll use the early stopping callback so early stopping will look at the validation loss.

## Result
I'll display the loss value to five decimal places format that with results. The first value returned by model.evaluate will be the loss and the second value will be the accuracy.For the esimation of accuracy the same thing will be done. Model.predict will return the probability estimation for the person being in the image.<br>  Loss and Accuracy: The model gains 0.69311 of loss and 50.22% accuracy on the test data.<br>
Confusion Matrix: The matrix containing correct and incorrect predictions in the form of true positives, false positives, false negatives and true negatives is called as "Confusion matrix". The rows represent actual and the columns represent predicted images of the dataset.<br>
True negative | 8
False negative| 10
True positive | 217
False positive| 213 <br>
Recall: Recall indicates the proportion of correct predictionof positives to the total number of positives.<br>
Recall=TP/(TP+FN). Car's recall comes out to be 40% i.e. out of all car's images 40% were predicted correctly and person's comes out to be 96% that means out of all the actuall images of the person 96% images have been detected correctly.<br>
Precision: Precision indicates the reliability of a model in predicting a class of interest. This model predicts the person's image with 50% precision and the cars's images with 44% of precision.<br>
f1 score: The f1-score is the harmonic mean of precision and recall. The model predicts the person's images with 0.66 and the car's images with 0.07 of f1-score.<br>
