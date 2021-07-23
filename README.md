# Image-Classification

# Pneumonia-Image-Classification
<br>- Course: Flatiron Data Science </br>
<br>- Pace: Self Paced </br>
<br>- Instructor: Jeff Herman </br>
<br>- Author: [Cody D. Freese](mailto:c_freese@ymail.com) </br>
![thermal_lung](https://user-images.githubusercontent.com/63601020/126825657-366f4988-26af-46c9-8f1f-7c4526137c61.jpg)
![chest_xray_image](https://user-images.githubusercontent.com/63601020/126825658-2288df8d-605c-4da9-a25b-b386f28874ee.jpg)


# Business-Understanding:
Predict a whether or not a provided chest x-ray image is positive for Pneumonia based infection using deep neural network.

# Data-Understanding:
Accompanying images provided by Kaggle
- The data was packaged into separate train, test, and validation sets. Each set was already prelabeled as either Normal or Pneumonia, the images themselves came in varying sizes, all were jpegs.

# Data-Preparation:
Originally the data provided a validation set, however this only consisted of 2 classes each with 8 images each. Therefore we had to creat a larger validation set from the training data. Validation data was used later in prediction function. Images needed to be rescaled to the same shape and pixalation.

# Modeling
I used Python in Jupyter Notebook along with Keras packages to build a neural network. Sequential class with 2D Convolution layer with relu activation, MaxPooling 2D layer, Flatten layer, a Dense layer with relu activation and final Dense layer with sigmoid activation. Compiled together with binary crossentropy as the loss function. A finetuned model that would checkpoint and save the best metrics and an early stop callback should it exceed 10 epochs.

# Evaluation:
Our metric for the the value of the model would be recall, as we do not want to misdiagnose someone healthy to be sick, or worse a sick person to be healthy.

# Deployment:
A prediction function was compiled and tested using the originally provided validation data.
