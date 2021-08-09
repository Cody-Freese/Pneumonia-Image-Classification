# Image-Classification

# Pneumonia-Image-Classification
<br>- Course: Flatiron Data Science </br>
<br>- Pace: Self Paced </br>
<br>- Instructor: Jeff Herman </br>
<br>- Author: [Cody D. Freese](mailto:c_freese@ymail.com) </br>

![pneumonia image](https://user-images.githubusercontent.com/63601020/128221821-f2c65ec1-8c6a-4313-9ee0-cbd1125d2b0c.jpeg) 
Pneumonia

![normal image](https://user-images.githubusercontent.com/63601020/128221843-09ddf683-4c58-4eb3-b11a-191e5ee40a93.jpeg)
Normal



# Business-Understanding:
- Predict a whether or not a provided chest x-ray image is positive for Pneumonia based infection using deep neural network.

# Data-Understanding:
-Accompanying images provided by Kaggle
- The data was packaged into separate train, test, and validation sets. Each set was already prelabeled as either Normal or Pneumonia, the images themselves came in varying sizes, all were jpegs.

# Data-Preparation:
- Originally the data provided a validation set, however this only consisted of 2 classes each with 8 images each. Therefore we had to create a larger validation set. I manually sorted them, putting all Pneumonia positive together and all Pneumonia Negative images together. Then train/test/validation splitting them. Training set of 70%, and the test and validation sets into 15% each. All images were rescaled from 0 to 1. Test data received light augmentation to extrapolate extra data that may be found from augmentation.

# Modeling
- I made several models to train, test and evaluate the data. 

- The first was a Multi-Layer Perceptron, a flattened layer with 5 Dense layers.

- A second model, a convoluted neural network with a max pooling layer, Flattened and run through the subsequent 5 layers.

- Third model had a pretrained base off of DenseNet201, Flattened and run through 5 layers.

- Each model was then Finetuned with a checkpoint and an early stopping protocol. This gave mildly different results but did not result in an overwhelming betterment of the original models.

# Evaluation:

| Metrics           | Loss   | Accuracy | Precision | Recall |
|-------------------|--------|----------|-----------|--------|
| MLP Original      | 26.40% | 88.40%   | 87.30%    | 89.87% |
| MLP Finetune      | 25.46% | 89.87%   | 89.87%    | 89.87  |
| CNN Original      | 17.15% | 94.09%   | 93.36%    | 94.94% |
| CNN Finetune      | 12.09% | 96.20%   | 96.60%    | 95.78% |
| Pretrain Original | 18.42% | 92.83%   | 94.32%    | 91.14% |
| Pretrain Finetune | 16.23% | 94.09%   | 99.06%    | 89.03% |

- All models performed with 88% or greater accuracy, 87% precision, 89% recall on the worst models. The metric to be monitored was recall as the risk of a False Negative would be disastrous in a pragmatic scenario. We do not want to tell a sick person they are healthy as pneumonia can be a deadly disease.
 
- For my final assessment I recommend deploying the CNN Finetune model in application for pneumonia detection.
 
# Deployment:
- These models can be used in an image detection program to be used by doctors to help them in a medical diagnosis. More data is needed to improve learning. 
