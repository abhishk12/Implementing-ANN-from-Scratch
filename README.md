# Implementation of Artificial Neural Network (ANN) from Scratch

**_This project is intended to learn Deep Learning core concepts. I've also deployed the same project by using CNN algorithm and **[tensorflow API](https://www.tensorflow.org/)**. You can find the deployed project **[here](https://github.com/abhishk12/Food-Nonfood-ImageClassifier)**_**.

## Introduction

In this project, I've implemented a Food/Non-food binary classification using **[Artificial Neural Network (ANN)](https://en.wikipedia.org/wiki/Artificial_neural_network "ANN")** from **scratch**. This project is taken from **[Kaggle Datasets](https://www.kaggle.com/trolukovich/food5k-image-dataset?select=evaluation "Dataset Link")** but the dataset is also available at **[this](https://www.epfl.ch/labs/mmspg/downloads/food-image-datasets/ "Original Dataset Link")** link. The images used for the dataset are scaled down to size of `64 X 64 X 3` and the model has 3 hidden layers and one output layer using sigmoid activation function. After evaluating the model gave an accuracy of `75.0%`.

## Dataset
The dataset used for the project is **[Food-5K](https://www.epfl.ch/labs/mmspg/downloads/food-image-datasets/  "Food-5K dataset link")**. This is a dataset containing 2500 food and 2500 non-food images. The whole dataset is divided in three parts: training, validation and evaluation. The naming convention is as follows:

> {ClassID}_{ImageID}.jpg

> ClassID: 0 or 1; 0 means non-food and 1 means food. 

> ImageID: ID of the image within the class.

## Data Preprocessing
The first step in data preprocessing is to convert the image into array of numbers which was done using OpenCV's [cv2.imread()](https://docs.opencv.org/3.4/d4/da8/group__imgcodecs.html#ga288b8b3da0892bd651fce07b3bbd3a56) function. After the conversion, the image was then resized to shape of `64 X 64 X 3`. Then the array was flattened to achieve a shape of `64*64*3 = (12288,m)` where "m" is the number of training examples. The last step in data preprocessing is to normalize the values in the flattened array. The normalization is done by dividing the array by `255`.

## Modelling
While initializing the parameters, I've used **"He weight initialization"** which simply divides the weights by `sqrt(2 / (No._of_neurons_in_previous_layer))`.
