# Image-Classification

# Pneumonia-Image-Classification
<br>- Course: Flatiron Data Science </br>
<br>- Pace: Self Paced </br>
<br>- Instructor: Jeff Herman </br>
<br>- Author: [Cody D. Freese](mailto:c_freese@ymail.com) </br>
<br>- Pneumonia
![pneumonia image](https://user-images.githubusercontent.com/63601020/128221821-f2c65ec1-8c6a-4313-9ee0-cbd1125d2b0c.jpeg)
<br>- Normal
![normal image](https://user-images.githubusercontent.com/63601020/128221843-09ddf683-4c58-4eb3-b11a-191e5ee40a93.jpeg)



# Business-Understanding:
Predict a whether or not a provided chest x-ray image is positive for Pneumonia based infection using deep neural network.

# Data-Understanding:
Accompanying images provided by Kaggle
- The data was packaged into separate train, test, and validation sets. Each set was already prelabeled as either Normal or Pneumonia, the images themselves came in varying sizes, all were jpegs.

# Data-Preparation:
Originally the data provided a validation set, however this only consisted of 2 classes each with 8 images each. Therefore we had to creat a larger validation set. I manually resorted them, putting all Pneumonia together and all Normal images together. Then train/test/validation splitting them. Training set of 70%, and the test and validation sets into 15% each. All images were rescaled from 0 to 1. Test data received light augmentation to extrapolate extra data that may be found from augmentation.

# Modeling
I made several models to train, test and evaluate the data. 

The first was a Multi-Layer Perceptron, a flattened layer with 5 Dense layers. 
A second model, a convoluted neural network with a max pooling layer, Flattened and run through the subsequent 5 layers.
Third model had a pretrained base off of DenseNet201, Flattened and run through 5 layers.
Each model was then Finetuned with a checkpoint and an early stopping protocol. This gave mildly different results but did not result in an overwhelming betterment of the original models.

# Evaluation:
All models performed with 90% or greater accuracy, 85% precision, 85% recall on the worst models. The metric to be monitored was loss as I wanted to exhaust the capability of the program to learn instead of defining a classification metric. Let the program learn to the best of its ability and see what the results are.

# Deployment:
These models can be used in an image detection program to be used by doctors to help them in a medical diagnosis. More data is needed to improve learning. 
