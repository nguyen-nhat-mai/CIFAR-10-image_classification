# CIFAR-10 image classification

This project is a part of Deep Learning course at CentraleSupelec

## Project description
The mission is to build and try networks (based on popular deep learning network architectures such as VGG, Resnet, ...) on [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html) to predict the class of the image. It is important to understand how data pre-process, parameter changes and architecture of networks affect the performance. The popular CIFAR-10 contain 60,000 images of size 32x32. Each image belongs to 1 out of 10 classes (airplane, automobile, bird, cat, deer, dog, frog, horse, trip, truck). The evaluation metric is accuracy score. A snapshot into the data is as followed:

![image](https://user-images.githubusercontent.com/85484281/215329375-80e3122b-967f-4f5b-a5a7-8a7625d220e1.png)

## Pre-processing and exploration
The dataset is standard with balanced labels which is good as a base to test and learn how each component affects the accuracy:

![image](https://user-images.githubusercontent.com/85484281/215471791-abcc1671-1fdf-431f-9344-e4861137c560.png)

Data are pre-processed in 3 stages:
1. Converted into tensors
2. Normalized
3. Augmented (randomly flipped, changed color/ brightness, etc.)

Noted that, the augmentation is only carried out on the training images, not the validation images

## Modelling
Popular networks are used:

**1. VGG16** became famous after the 2014 ImageNet Challenge. Compared to previous models, VGG16 increases the depth of the network (add more non-linearity to capture the complex relationships) and uses smaller filters (prevent overfitting). Thus, it helps improve the accuracy. This network, however, easily suffers from vanishing gradient due to its depth.

![image](https://user-images.githubusercontent.com/85484281/215480905-4738d0be-8e4a-433d-a02f-147d7565b218.png)

**2. Resnet** being tested

Evaluation metrics used are:
- Accuracy score = # image correctly labeled / # image (100% means all the predicted labels are correct)
- Cross entrophy loss = 
-
## Findings

## References
https://github.com/Armour/pytorch-nn-practice/blob/master/utils/meanstd.py

https://blog.paperspace.com/vgg-from-scratch-pytorch/

https://arxiv.org/pdf/1409.1556.pdf
