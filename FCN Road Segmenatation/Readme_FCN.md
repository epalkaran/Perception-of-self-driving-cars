
# Fully Convolutiona Network #
---

Convolutional networks are powerful visual models that yield hierarchies of features. We show that convolutional networks by themselves, trained end-to-end, pixels-to-pixels, exceed the state-of-the-art in semantic segmentation. Our key insight is to build "fully convolutional" networks that take input of arbitrary size and produce correspondingly-sized output with efficient inference and learning. We define and detail the space of fully convolutional networks, explain their application to spatially dense prediction tasks, and draw connections to prior models. We adapt contemporary classification networks (AlexNet, the VGG net, and GoogLeNet) into fully convolutional networks and transfer their learned representations by fine-tuning to the segmentation task. We then define a novel architecture that combines semantic information from a deep, coarse layer with appearance information from a shallow, fine layer to produce accurate and detailed segmentations.

### Why FCN? ###

FCN is a network that does not contain any “Dense” layers (as in traditional CNNs) instead it contains 1x1 convolutions that perform the task of fully connected layers (Dense layers). This technique introduces a method of segmentation end to end
i.e. when an image is input to an FCN module it will output the segmentation it is trained for without any data preprocessing or postprocessing being required.

### FCN Overview ###

For FCN we need a backbone network which is a image classification network called VGG Network. It is composed of a number of convolutional blocks which are placed sequentially ot each other.Each block consists of two convolutional layers followed by a max pooling layer. We extract the output of last three convolutional blocks called **POOL3,POOL4,POOL5** .
We upsample POOL5 by 2x and add it to the output of POOL4.The result is then upsampled 2x and added to the output of POOL3. The result is finally upsampled 8 times.This final output is the segmentation mask.This is the FCN-8 architecture.This architecture allows for identifying finer structures in the image

### Dataset ###

The dataset used to train our model is [KITTI Road Dataset](http://www.cvlibs.net/datasets/kitti/)
<!-- <p>Convolutional networks are powerful visual models that yield hierarchies of features. We show that convolutional networks by themselves, trained end-to-end, pixels-to-pixels, exceed the state-of-the-art in semantic segmentation. Our key insight is to build "fully convolutional" networks that take input of arbitrary size and produce correspondingly-sized output with efficient inference and learning. We define and detail the space of fully convolutional networks, explain their application to spatially dense prediction tasks, and draw connections to prior models. We adapt contemporary classification networks (AlexNet, the VGG net, and GoogLeNet) into fully convolutional networks and transfer their learned representations by fine-tuning to the segmentation task. We then define a novel architecture that combines semantic information from a deep, coarse layer with appearance information from a shallow, fine layer to produce accurate and detailed segmentations.</p> -->
