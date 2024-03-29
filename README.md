# Automated Melanoma Detection using Deep Learning

Project presented to obtain the Master Degree in Economics, Finance and Computer Science

# Abstract

Skin cancer is one of the leading causes of deaths worldwide. Early detection of the disease improves the patient’s prognosis. The present research’s main objective is to obtain a Deep Learning model for melanoma detection. The HAM10000 dermatological repository with 10 015 images of seven different types of skin lesions is used. Three models based on Convolutional Neural Networks (Xception, ResNet, MobileNet) and three based on Vision  Transformers Neural Networks (ViT-B32, ViT-B16, ViT-L32) are trained. Models based on the second architecture obtains better results in lesion classification and melanoma-specific detection. A model with results in the range
of those described in the literature for skin cancer classification is obtained.

## KeyWords

Deep Learning. Image classification. Transfer learning. Convolutional Neural Network. Vision Transformers

## Sections

1. [Database and Data Augmentation](https://github.com/FrankARicardo/Melanoma/tree/main/1.%20Database%20and%20Data%20Augmentation)
2. [Training stages](https://github.com/FrankARicardo/Melanoma/tree/main/2.%20Training%20design)
3. [Convolutional Neural Networks](https://github.com/FrankARicardo/Melanoma/tree/main/3.%20Convolutional%20Neural%20Networks)
4. [Vision Transformers](https://github.com/FrankARicardo/Melanoma/tree/main/4.%20Vision%20Transformers)
5. [Results comparision](https://github.com/FrankARicardo/Melanoma/tree/main/5.%20Results%20comparision)

## Code details

All code is implemented in TensorFlow 2.8

Data augmentation in training is implemented with [ImageDataGenerator](https://www.tensorflow.org/api_docs/python/tf/keras/preprocessing/image/ImageDataGenerator)

Data is loaded from csv files, using [ImageDataGenerator.flow_from_dataframe](https://www.tensorflow.org/api_docs/python/tf/keras/preprocessing/image/ImageDataGenerator)




