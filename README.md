# PointNet++ Modified

This repo is forked from [yanx27/Pointnet_Pointnet2_pytorch](https://github.com/yanx27/Pointnet_Pointnet2_pytorch). It provides a modified implementation for PointNet and PointNet++ in PyTorch.

## Modifications

Three sections of the network have been modified for experiment purposes:

* Sampling Layer: Distance Farthest Sampling (DFS) => Feature Farthest Sampling (FPS)
* Gouping Layer: Ball Query => kNN

* Interpolation: Concatenation of three nearest point => Duplicate the nearest point

## Result

### Classification

| Model (With Normal, 50 Epochs) | Instance Accuracy | Class Accuracy | Memory Usage (Titan X Pascal) | Time (min) |
| ------------------------------ | ----------------- | -------------- | ----------------------------- | ---------- |
| PointNet++_MSG (Original)      | 92.4              | 88.9           | 12147M                        | 6.90       |
| PointNet++_MSG_FPS_kNN         | 92.4              | 88.9           | 11875M                        | 7.34       |
| PointNet++_MSG_FPS             | 92.2              | 89.1           | 12129M                        | 6.25       |
| PointNet++_MSG_kNN             | 91.9              | 90             | 11873M                        | 6.72       |

### Part Segmentation

| Model (20 Epochs)            | Instance Avg IoU | Class Avg IoU | Memory Usage | Avg Time per Epoch (min) |
| ---------------------------- | ---------------- | ------------- | ------------ | ------------------------ |
| PointNet++_MSG (Original)    | 83.5             | 79.0          | 9827M        | 14.56                    |
| PointNet++_MSG_Duplicate     | 82.9             | 79.7          | 9785M        | 12.5                     |
| PointNet++_MSG_FPS_Duplicate | 83.1             | 77.9          | 9685M        | 12.47                    |
| PointNet++_MSG_kNN_Duplicate | 83.0             | 79.2          | 9913M        | 12.55                    |

## Reference

[yanx27/Pointnet_Pointnet2_pytorch](https://github.com/yanx27/Pointnet_Pointnet2_pytorch)



