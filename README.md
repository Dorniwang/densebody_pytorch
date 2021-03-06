# densebody_pytorch
PyTorch implementation of CloudWalk's recent paper [DenseBody](https://arxiv.org/abs/1903.10153v3)

![paper teaser](teaser/teaser.jpg)

### Update Notes
Thanks for the contribution of this [PR](https://github.com/Lotayou/densebody_pytorch/pull/6) commited by [radvani](https://github.com/radvani), the SMPL UV map color inconsistency issue is now solved. Meanwhile I will be working on the transformation of some core algorithms from numpy to torch, as well as performing necessary code reformatting and unit tests to eliminate any potential errors. It may take a few days, but I'm sure it will be worthwhile.

The upcoming project will feature more concise user interfaces and better class organizations, stay tuned for more update. 
For those who already forked my project, the original code is now temporarily hosted in the `legacy` branch, and will be removed after the code reformatting is complete.

### Prerequisites
```
Ubuntu 18.04
CUDA 9.0
Python 3.6
PyTorch 1.0.0
chumpy (For converting SMPL model to basic numpy arrays)
spacepy, h5py (For processing Human36m cdf annotations)
```

(Optional) Install [torch-batched-svd](https://github.com/KinglittleQ/torch-batch-svd) for speedup (Only tested under Ubuntu system).


### TODO List
- [x] Creating ground truth UV position maps for Human36m dataset.
    - [x] [20190329]() Finish UV data processing.
    - [x] [20190331]() Align SMPL mesh with input image.
    - [x] [20190404]() Data washing: Image resize to 256*256 and 2D annotation compensation.
    - [x] [Testing]() Generate and save UV position map.
        - [ ] [Proceeding]() Checking validity through resampling and mesh reconstruction...
        - [ ] Making UV_map generation module a separate class.
    
- [ ] Finish baseline model training
    - [ ] Testing with several new loss functions.
    - [ ] Testing with different networks.
- [ ] Report 3D reconstruction results.
    - [ ] Setup evaluation protocal and MPJPE-PA metrics.


### Current Progress
Finish UV texture map processing. Here's the result:

![UV_map](teaser/SMPL_UV_map.png)

Align SMPL meshes with input images. Here are some results:

![Ground Truth Image](teaser/im_gt_0.png)
![Aligned Mesh Image](teaser/im_mask_0.png)
![Generated UV map](teaser/UV_position_map_0.png)

![Ground Truth Image](teaser/im_gt_1.png)
![Aligned Mesh Image](teaser/im_mask_1.png)
![Generated UV map](teaser/UV_position_map_1.png)

### Citation
Please consider citing the following paper if you find this project useful.

[DenseBody: Directly Regressing Dense 3D Human Pose and Shape From a Single Color Image](https://arxiv.org/abs/1903.10153v3)

### Disclaimer
Please note that this is an unofficial implementation free for non-commercial usage only. For commercial cooperation please contact the original authors.
