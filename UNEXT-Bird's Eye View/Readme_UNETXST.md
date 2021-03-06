# UNETXST #
---

In recent years, the development of automated vehicles (AVs) has received substantial attention from both research and industry. One of the key elements of automated driving is the accurate perception of an AV’s environment. It is essential for planning safe and efficient behavior. Different types of environment representations can be computed, e.g. object lists or occupancy grids. Both require information on the world coordinates of elements in the environment. Among the different types of sensors commonly used to achieve an understanding of the environment,cameras are popular due to low cost and well-established computer vision techniques. Since monocular cameras can only provide information on locations in the image plane, a perspective transformation can be applied to images that results in a top-down or bird’s eye view (BEV). It is an approximation of the same scene as seen from a perspective in which the image plane aligns with the ground plane in front of the camera. The method used for transforming camera images to BEV is commonly referred to as Inverse Perspective Mapping (IPM).

### Inverse Perspective Mapping(IPM) ###

IPM assumes the world to be flat. Any three-dimensional object and changing road elevations violate this assumption. Mapping all pixels to a flat plane thus results in strong visual distortions of such objects. This impedes our goal of accurately locating objects such as other vehicles and vulnerable road users in the vehicle’s environment. For this reason, images transformed through IPM often only serve as input to algorithms for lane detection or free space computation, for which the flat world assumption is often reasonable.
 
 ### The Model ###
UNETXST is a methodology to obtain BEV images that are not subject to the errors introduced by the flatness-assumption underlying IPM. Instead of trying to make simulated images look more realistic, we remove mostly unnecessary texture from real-world data by computing semantically segmented camera images. We show how their use as input to our algorithm allows us to train a neural network on synthetic data only, while still being able to successfully perform the desired task on real-world data. With semantically segmented input, the algorithm has access to class information and is thus able to incorporate these into the correction of images produced by IPM. The output is a semantically segmented BEV of the input scene. Since the object shapes are preserved, the output can not only be used for determining free space but also to locate dynamic objects. In addition, the semantically segmented BEV images contain a color-coding for unknown areas, which are occluded in the original camera image. The _uNetXST_ model achieves the highest MIoU score on the validation set as it benefits from being able to extract features from the non-transformed camera images, before perspective errors are introduced by IPM.
### Architecture###
<img src="../images_architecture/unist.jpg" width="500" height="600">

### Dataset ###

[Semantic Segmentation Dataset](https://www.kaggle.com/datasets/sakshaymahna/semantic-segmentation-bev)