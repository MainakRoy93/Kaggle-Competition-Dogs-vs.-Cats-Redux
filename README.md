# Kaggle-Competition-Dogs-vs.-Cats-Redux
This reporsitory contains code and documentation for the predictive challenge on Kaggle, which required an algorithm to predict whether an image contained a cat or dog. I used a transfer learning approach to solve this challenge

[Kaggle Competition Link](https://www.kaggle.com/c/dogs-vs-cats-redux-kernels-edition)


# Transfer Learning
Transfer learning (TL) is a research problem in machine learning (ML) that focuses on storing knowledge gained while solving one problem and applying it to a different but related problem.For example, knowledge gained while learning to recognize cars could apply when trying to recognize trucks.

# Models Used
## VGG16
GG16 is a convolutional neural network model proposed by K. Simonyan and A. Zisserman from the University of Oxford in the paper “Very Deep Convolutional Networks for Large-Scale Image Recognition”. The model achieves 92.7% top-5 test accuracy in ImageNet, which is a dataset of over 14 million images belonging to 1000 classes. It was one of the famous model submitted to ILSVRC-2014. It makes the improvement over AlexNet by replacing large kernel-sized filters (11 and 5 in the first and second convolutional layer, respectively) with multiple 3×3 kernel-sized filters one after another. VGG16 was trained for weeks and was using NVIDIA Titan Black GPU’s.

### VGG16 Architecture
[Architecture Image](https://github.com/MainakRoy93/Kaggle-Competition-Dogs-vs.-Cats-Redux/blob/master/Images/2020-01-26_11h31_32.png?raw=true "Optional Title")
