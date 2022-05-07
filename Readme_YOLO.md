# YOLO(You Only Look Once) #
---

YOLO is a Deep Learning architecture proposed by Joseph Redmon, Santosh Divvala, Ross
Girshick, Ali Farhadi in the paper ‘You Only Look Once: Unified, Real-Time Object Detection’ uses a totally different approach.

### Why YOLO? ###

Biggest advantages over other techniques:

- Speed (45 frames per second — better than realtime)
- Network understands generalized object representation (This allowed them to train the network on real world images and predictions on artwork was still fairly accurate).
- Faster version (with smaller architecture) — 155 frames per sec but is less accurate.
- [Open Source](https://pjreddie.com/darknet/yolo/)

### Basic Architecture ###
First the image is passed through a CNN to obtain a 19X19 matrix that contains the location of objects in the image and a special vector that contains additional information about the image.
The YOLO algorithm can be divided into three stages:
1.Anchor Boxes: Helps in identifying multiple objects in the same cell. 
2.Intersection Over Union:Helps in isolating the bounding box for each object using non maximum suppression.
3.Bounding Box Prediction: Predicts the most likely bounding box for a certain object.
The algorithm applies a single neural network to the entire full image. Then this network divides that image into regions which provides the bounding boxes and also predicts probabilities for each region. These generated bounding boxes are weighted by the predicted probabilities.

### Dataset ###

[Lyft 3D Object Detection](https://www.kaggle.com/c/3d-object-detection-for-autonomous-vehicles)

