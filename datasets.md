# Datasets Introduction

## nuScenes
- officially split: 700/150/150
- 1000 seqs, each lasts 20 seconds
- 3D occupancy annotations: provided by surroundocc
- voxel grids: [-50m, 50m], [-50m, 50m], [-5m, 3m]; rosulution: 200×200×16
- labels: 18 classes (16 semantic, 1 empty and 1 unknown classes)


 
## KITTI-360
- containing 9 long sequences, officially split into 7/1/1 (8487/1812/2566 key frames)
- 3D occupancy annotations: provided by SSCBench-KITTI-360
- voxel grids: 51.2 × 51.2 × 6.4m^3 in front of the ego car; resolution:256×256×32
- labels: 19 classes (18 semantic, 1 empty)
