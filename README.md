# CIFAR-10 image classification

This project is a part of Deep Learning course at CentraleSupelec

## Project description
The mission is to build and try networks (based on popular deep learning network architectures such as VGG, Resnet, ...) on [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html) to predict the class of the image. The popular CIFAR-10 contain 60,000 images of size 32x32. Each image belongs to 1 out of 10 classes (airplane, automobile, bird, cat, deer, dog, frog, horse, trip, truck). The evaluation metric is accuracy score. A snapshot into the data is as followed:

![image](https://user-images.githubusercontent.com/85484281/215329375-80e3122b-967f-4f5b-a5a7-8a7625d220e1.png)

## Pre-processing and exploration
The dataset is quite standard with balanced labels:

![image](https://user-images.githubusercontent.com/85484281/215471791-abcc1671-1fdf-431f-9344-e4861137c560.png)

Data are normalized and augmented before fed into the models

## Modelling
Popular networks are used:

*1. VGG16*

Evaluation metrics used are:
- Accuracy score = # image correctly labeled / # image (100% means all the predicted labels are correct)
- Cross entrophy loss = 
## Findings

## References
https://github.com/Armour/pytorch-nn-practice/blob/master/utils/meanstd.py

https://blog.paperspace.com/vgg-from-scratch-pytorch/
