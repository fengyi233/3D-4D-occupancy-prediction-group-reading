## Occ3D: A Large-Scale 3D Occupancy Prediction Benchmark for Autonomous Driving
### Abstract
- develop a label generation pipeline that produces dense, visibility-aware labels
- 3 stages: voxel densification, occlusion reasoning, and image-guided voxel refinement.
- establish 2 benchmarks: Occ3D-Waymo and Occ3D-nuScenes
- propose CTF-Occ network


### Motivation
compared with 3D object detection:
- 3D bounding box representation erases the geometric details of objects
- uncommon categories are often ignored and not labeled in the datasets

### Occ3D-nuScenes Dataset
- 600 scenes for training, 150 scenes for validation, and 150 for testing, totaling 40,000 frames
- 16 common classes, an additional general object (GO) class
- voxel size: [0.4m,0.4m,0.4m]
- scene range: [-40m, -40m, -1m, 40m, 40m, 5.4m]

