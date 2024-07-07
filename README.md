## Counterfeit IC Detection


### Overview
Counterfeit Integrated Circuits (ICs) pose a significant threat to various industries, including electronics manufacturing, telecommunications, and aerospace. This project proposes a novel approach for counterfeit IC detection using Convolutional Neural Networks (CNNs). Our custom-designed model, inspired by the VGG16 architecture, aims to enhance the reliability and security of electronic systems against the threat of counterfeit ICs.


### Table of Contents
- [Methodology](#methodology)
  - [Data Preparation](#data-preparation)
  - [Models](#models)
  - [Proposed Model](#proposed-model)
- [Results](#results)
- [Future Work](#future-work)


### Methodology

#### Data Preparation
The dataset consists of 85 images, with 50 approved and 35 counterfeit images. Due to the small dataset size, extensive data augmentation was applied to enhance model generalization. Images were resized to (960, 720, 3) and various augmentation techniques such as random flips and rotations were employed, increasing the training set to 430 images.

#### Models
We explored several models, including AlexNet and VGG16:
- **AlexNet**: Achieved a training and validation accuracy of 58.8%. The model was found to be too simplistic for this task.
- **VGG16**: Achieved a training accuracy of 82% and validation accuracy of 70%. Although it performed better than AlexNet, it showed an increase in validation loss over epochs, indicating potential overfitting.

#### Proposed Model
Our custom model incorporates 8 convolutional layers with (3, 3) kernel sizes, followed by max-pooling, ReLU activation, and batch normalization layers. It also includes 3 fully connected layers. The difference of this model to VGG16 is the number of convolutional layers are decreased, and there are no immediate CNN layers after each other. They are separated by pooling and batch norm layers. All the dropout layers were also removed. The intuition behind choosing this architecture was that we tried to choose a model which is slightly complex than AlexNet but at the same time not as complex as VGG16


### Results
The training process involved 100 epochs, a learning rate of 0.002, and early stopping to prevent overfitting. The final model showed significant improvement over both AlexNet and VGG16, with a validation accuracy of 94% and a recall of 86% for counterfeit class detection.


### Future Work
Future enhancements could include exploring brightness and contrast augmentations, as well as integrating more advanced data preprocessing techniques to further improve model performance and generalization.