# CIFAR-10 image classification (in process)

## Project description
The mission is to build and try networks (based on popular deep learning network architectures such as VGG, Resnet, ...) on [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html) to predict the class of the image. It is important to understand how data pre-process, parameter changes and architecture of networks affect the performance. The popular CIFAR-10 contain 60,000 images of size 32x32. Each image belongs to 1 out of 10 classes (airplane, automobile, bird, cat, deer, dog, frog, horse, trip, truck). The evaluation metric is accuracy score. A snapshot into the data is as followed:

![image](https://user-images.githubusercontent.com/85484281/215329375-80e3122b-967f-4f5b-a5a7-8a7625d220e1.png)

## Pre-processing and exploration
The dataset is standard with balanced labels. This is good as a base to test and learn how each component affects the accuracy:

![image](https://user-images.githubusercontent.com/85484281/215471791-abcc1671-1fdf-431f-9344-e4861137c560.png)

Data are pre-processed in 3 stages:
1. Converted into tensors
2. Normalized
3. Augmented (randomly flipped, changed color/ brightness, etc.)

Noted that, the augmentation is only carried out on the training images, not the validation images

## Modelling
Popular networks are used:

**1. VGG16** became famous after the 2014 ImageNet Challenge. Compared to previous models, VGG16 increases the depth of the network (add more non-linearity to capture the complex relationships) and uses smaller filters (prevent overfitting). Thus, it helps improve the accuracy. This network, however, easily suffers from vanishing gradient due to its depth.

![image](https://user-images.githubusercontent.com/85484281/216814264-bbc4fa4b-32bf-443e-8b20-b53ba13a9ca4.png)

**2. VGG13** is a modified version of VGG16 to adapt to the small image size in this case (32x32). The last 3 cnn layers (3x3 conv 512) are removed and the number of nodes in fully connected (fc) layers are reduced

![image](https://user-images.githubusercontent.com/85484281/216815184-1bf744ea-0492-464f-8326-f30246466b71.png)

**3. Resnet** being tested

A deep dive into how the cnn layers work is as followed (take VGG16 as an example)

![image](https://user-images.githubusercontent.com/85484281/216068064-0879c7df-831f-4f1c-8656-070e6e111262.png)

Evaluation metrics used are:
- Accuracy score = # image correctly labeled / # image (100% means all the predicted labels are correct)
- Cross entrophy loss (CEL) measures the difference between true distribution and predicted distribution. The closer CEL is to 0, the more accurate the model is. Example is as followed:

![image](https://user-images.githubusercontent.com/85484281/215549332-c4f86e32-2861-4404-8616-f026545b52ca.png)

## Findings
Via trial and error, I observe the followings:
- Normalizing and augmenting images do affect the accuracy. They help improve the accuracy in this case.

![image](https://user-images.githubusercontent.com/85484281/216837953-85bafc79-c7bf-4f10-bb74-20683bfde0eb.png)

- Choosing an approriate optimization method and learning rate is critical. Details are noted for each case below.

![image](https://user-images.githubusercontent.com/85484281/217895840-e2a143d4-70a0-48ea-88e3-002e9d844121.png)

## References
https://github.com/Armour/pytorch-nn-practice/blob/master/utils/meanstd.py

https://blog.paperspace.com/vgg-from-scratch-pytorch/

https://arxiv.org/pdf/1409.1556.pdf

https://debuggercafe.com/visualizing-filters-and-feature-maps-in-convolutional-neural-networks-using-pytorch/
