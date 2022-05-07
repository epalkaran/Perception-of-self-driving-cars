# SFA3D(Super Fast and Accurate 3D) Object Detection #
---

To convert the LIDAR sensor data into a 3D representation of the objects detected by the sensor we use the SFA3D(Super Fast and Accurate 3D) Object Detection technique.The input provided is a bird’s eye view of the LIDAR data, the network predicts the different objects present in it and also classifies them.

### structure ###

1. **Keypoint FPN(Feature Pyramid Network)** :  Keypoint Feature Pyramid Network (KFPN) to detect scale-invariant keypoints in the point-wise space. Assuming we have F scale feature maps, we first resize each scale f, 1 < f < F back to the size of maximal scale,
which yields the feature maps f , 1< f< F. Then, we generate soft weight by a softmax operation to denote the importance
of each scale. The finally scale-space score map Sscore is obtained by linear weighing sum. 
2. **The different Losses** : 
- _Focal Loss_ : Focal loss applies a modulating term to the cross entropy loss in order to focus learning on hard misclassified examples. It is a dynamically scaled cross entropy loss, where the scaling factor decays to zero as confidence in the correct class increases.
- _L1 Loss_ : L1 Loss function stands for Least Absolute Deviations. Also known as LAD. L1 Loss Function is used to minimize the error which is the sum of the all the absolute differences between the true value and the predicted value.
3. **Learning Rate Scheduling Technique** : Learning rate decay is a technique for training modern neural networks. It starts training the network with a large learning rate and then slowly reducing/decaying it until local minima is obtained. It is empirically observed to help both optimization and generalization.

### Dataset ###

[KITTI 3D Object Detection Dataset](https://www.kaggle.com/datasets/garymk/kitti-3d-object-detection-dataset)