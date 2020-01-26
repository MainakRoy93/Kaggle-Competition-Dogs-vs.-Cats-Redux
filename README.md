# Kaggle-Competition-Dogs-vs.-Cats-Redux
This reporsitory contains code and documentation for the predictive challenge on Kaggle, which required an algorithm to predict whether an image contained a cat or dog. I used a transfer learning approach to solve this challenge

[Kaggle Competition Link](https://www.kaggle.com/c/dogs-vs-cats-redux-kernels-edition)


# Transfer Learning
Transfer learning (TL) is a research problem in machine learning (ML) that focuses on storing knowledge gained while solving one problem and applying it to a different but related problem.For example, knowledge gained while learning to recognize cars could apply when trying to recognize trucks.

# Models Used
## VGG16
GG16 is a convolutional neural network model proposed by K. Simonyan and A. Zisserman from the University of Oxford in the paper “Very Deep Convolutional Networks for Large-Scale Image Recognition”. The model achieves 92.7% top-5 test accuracy in ImageNet, which is a dataset of over 14 million images belonging to 1000 classes. It was one of the famous model submitted to ILSVRC-2014. It makes the improvement over AlexNet by replacing large kernel-sized filters (11 and 5 in the first and second convolutional layer, respectively) with multiple 3×3 kernel-sized filters one after another. VGG16 was trained for weeks and was using NVIDIA Titan Black GPU’s.

### VGG16 Architecture
![Architecture Image](https://github.com/MainakRoy93/Kaggle-Competition-Dogs-vs.-Cats-Redux/blob/master/Images/2020-01-26_11h31_32.png?raw=true "Optional Title")

The input to cov1 layer is of fixed size 224 x 224 RGB image. The image is passed through a stack of convolutional (conv.) layers, where the filters were used with a very small receptive field: 3×3 (which is the smallest size to capture the notion of left/right, up/down, center). In one of the configurations, it also utilizes 1×1 convolution filters, which can be seen as a linear transformation of the input channels (followed by non-linearity). The convolution stride is fixed to 1 pixel; the spatial padding of conv. layer input is such that the spatial resolution is preserved after convolution, i.e. the padding is 1-pixel for 3×3 conv. layers. Spatial pooling is carried out by five max-pooling layers, which follow some of the conv.  layers (not all the conv. layers are followed by max-pooling). Max-pooling is performed over a 2×2 pixel window, with stride 2.

Three Fully-Connected (FC) layers follow a stack of convolutional layers (which has a different depth in different architectures): the first two have 4096 channels each, the third performs 1000-way ILSVRC classification and thus contains 1000 channels (one for each class). The final layer is the soft-max layer. The configuration of the fully connected layers is the same in all networks.

All hidden layers are equipped with the rectification (ReLU) non-linearity.

## ResNet50
ResNet-50 is a pretrained Deep Learning model for image classification of the Convolutional Neural Network(CNN, or ConvNet), which is a class of deep neural networks, most commonly applied to analyzing visual imagery. ResNet-50 is 50 layers deep and is trained on a million images of 1000 categories from the ImageNet database.

### Resnet50 Architecture
![Resnet Arch](https://github.com/MainakRoy93/Kaggle-Competition-Dogs-vs.-Cats-Redux/blob/master/Images/resnet50.png?raw=true "Optional Title")
ResNet stands for Residual Network and more specifically it is of a Residual Neural Network architecture. What characterizes a residual network is its identity connections. Identity connections takes the input directly to the end of each residual block, as shown below with the curved arrow:

Specifically, the ResNet-50 model consists of 5 stages each with a residual block. Each residual block has 3 layers with both 1x1 and 3x3 convolutions. The concept of residual blocks is quite simple. In traditional neural networks, each layer feeds into the next layer. In a network with residual blocks, each layer feeds into the next layer and directly into the layers about 2–3 hops away, called identity connections.

## Training Approaches
### Training only the fully connected layer
This is by far the fastest approach, where only the last fully connceted layers are trained as per our requirement, while all the other parameters are used as defined in the pre-trained model. Below us the performance of VGG16 when this approach is used
![IMage](https://github.com/MainakRoy93/Kaggle-Competition-Dogs-vs.-Cats-Redux/blob/master/Images/2020-01-26_12h37_00.png?raw=true "Optional Title")


