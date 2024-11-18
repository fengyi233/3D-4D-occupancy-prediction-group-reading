# Paper Reading -- 3D Occupancy Prediction 


---
## PLEASE USE THE FOLLOWING TEMPLATE：
## title
### Abstract
Describe what the paper have done, training srategy (supervised/unsupervised), system inputs and outputs, and application scenarios. 

### Motivation
Very important. 
Clarify the motivation behind the paper, and the comparison with prior arts.

### Framework Structure
Using screenshots if neccessary. Directly ctrlC+V. 
Provide the network details. 


### Methodology
Implementation details of contributions. Description of novel ideas. 


### Experiments
#### Metrics
#### Datasets
#### Performances

Metrics and Datasets can be ommitted if former papers have already clarified. 



---


## MonoScene: Monocular 3D Semantic Scene Completion

### Abstract
Pioneering work of 3d occ pred. 

- propose Semantic Scene Completion (SSC) task 
- supervised
- Input: single rgb
- Output: semantic + occupancy
- indoor (NYUv2) and outdoor (SemanticKITTI)


### Motivation
"Different from the SSC literature, relying on 2.5 or 3D input, we solve the complex problem of 2D to 3D scene reconstruction while jointly inferring its semantics."

"Subsequently, many algorithms use dedicated depth sensors such as Lidar [36, 50, 62] or depth cameras [2, 15, 19], easing the 3D estimation problem. These sensors are often more expensive, less compact and more intrusive than cameras which are widely spread and shipped in smartphones, drones, cars, etc. Thus, being able to estimate a 3D scene from an image would pave the way for new applications."


### Framework Structure
![](figs/monoscene-1.png)

RGB $\Rightarrow$ **EfficientNetB7** $\Rightarrow$ 2D features  $\Rightarrow$ **FLoSP** $\Rightarrow$ 3D features $\Rightarrow$ **3D UNet (inner: 3D CRP)** $\Rightarrow$ completion head $\Rightarrow$ semantic occupancy.

### Methodology

#### Features Line of Sight Projection (FLoSP)
Lifting 2D features to 3D.
![](figs/monoscene-2.png)


#### 3D Context Relation Prior (3D CRP)
Not important. 

#### Losses
1. Scene-Class Affinity Loss
![](figs/monoscene-3.png)


### Experiments

#### Metrics
IoU for scene completion
mIoU for semantic scene completion

#### Datasets
1. NYUv2. Not important.
2. SemanticKITTI. SemanticKITTI [3] holds outdoor Lidar scans voxelized as 256x256x32 grid of 0.2m voxels, labeled with 21 classes (19 semantics, 1 free, 1 unknown).


#### Performances
![](https://s3.hedgedoc.org/hd1-demo/uploads/8dee4752-7c0d-4d5f-a7a7-05f0b93c8084.png)

---
## SurroundOcc: Multi-Camera 3D Occupancy Prediction for Autonomous Driving
### Abstract

- supervised learning
- input: multi-camera images
- output: dense semantic occupancy prediction
- provide a way to generate occ ground truth


### Motivation
- LiDAR
suffers from high-cost sensors and sparse scanned points.

- Multi-camera 3D object detection
suffers from the long-tail problem and difficult to recognize all classes of objects in the real world.
have difficulty describing real-world objects of **arbitrary shapes** and infinite classes.

- Depth maps
only predict the nearest occupied point in each optical ray and are unable to recover the occluded parts of the 3D scene.

- 3D occupancy representation:
naturally guarantees the multicamera geometry consistency and is able to recover occluded parts.
flexible to extend to other 3D downstream tasks


### Framework Structure
![](https://s3.hedgedoc.org/hd1-demo/uploads/6f59f26e-1a2c-4a43-a2da-268ab739c770.png)



### Methodology
Implementation details of contributions. Description of novel ideas. 


### Experiments
#### Metrics
#### Datasets
#### Performances

Metrics and Datasets can be ommitted if former papers have already clarified. 

---
