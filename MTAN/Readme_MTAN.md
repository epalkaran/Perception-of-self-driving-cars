# MTAN(Multi Task Attention Network) #
---

In Machine Learning (ML), we typically care about optimizing for a particular metric, whether this is a score on a certain benchmark or a business KPI. In order to do this, we generally train a single model or an ensemble of models to perform our desired task. We then fine-tune and tweak these models until their performance no longer increases. While we can generally achieve acceptable performance this way, by being laser-focused on our single task, we ignore information that might help us do even better on the metric we care about. Specifically, this information comes from the training signals of related tasks. By sharing representations between related tasks, we can enable our model to generalize better on our original task. This approach is called Multi-Task Learning (MTL).
### Architecture ###
<img src="../images_architecture/MTAN.jpg" width="500" height="600">

### Attenion Focusing ###

If a task is very noisy or data is limited and high-dimensional, it can be difficult for a model to differentiate between relevant and irrelevant features. MTL can help the model focus its attention on those features that actually matter as other tasks will provide additional evidence for the relevance or irrelevance of those features.

### Challenges ###

Compared to standard single-task learning, training multiple tasks whilst successfully learning a shared representation poses two key challenges:

i) **Network Architecture (how to share)**: A multi-task learning architecture should express both task-shared and task-specific features. In this way, the network is encouraged to learn a generalisable representation (to avoid over-fitting), whilst also providing the ability to learn features tailored to each task (to avoid under-fitting).
ii) **Loss Function (how to balance tasks)**: A multi-task loss function, which weights the relative contributions of each task, should enable learning of all tasks with equal importance, without allowing easier tasks to dominate. Manual tuning of loss weights is tedious, and it is preferable to automatically learn the weights, or design a network which is robust to different weights.