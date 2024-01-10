
Come from NeRF : 
[[NeRF, Representing Scenes as Neural Radiance Fields for View Synthesis]]





Create them :
[[3D Gaussian Splattingfor Real-Time Radiance Field Rendering]]
`python convert.py -s ./dataset/test_boule_1/`
`python train.py -s ./dataset/test_boule_1/ -m ./output/test_boule_1/`




Gaussian to pointcloud :
`cd /mnt/partition_deux/gaussian-splatting`
`python gs_to_pointcloud.py -s ./output/mont_3/`


Gaussian to mesh :



Promising : 
[[SuGaR  Surface-Aligned Gaussian Splatting for Efficient 3D Mesh Reconstruction and High-Quality Mesh Rendering]]


Too heavy (based on poisson surface reconstruction)
[[Flexible Techniques for Differentiable Rendering with 3D Gaussians]]



Best way to poisson surface reconstruction : 
Stochastic Poisson Surface Reconstruction
https://arxiv.org/abs/2206.15236



Light them :
https://github.com/VITA-Group/LightGaussian#option-2-sh-distillation


Deform them :
PhysGaussian: Physics-Integrated 3D Gaussians for Generative Dynamics
https://arxiv.org/pdf/2311.12198.pdf



Edit them : 
https://github.com/playcanvas/super-splat



Reduce noisy 3D gaussians :
GS-SLAM: Dense Visual SLAM with 3D Gaussian Splatting
https://arxiv.org/pdf/2311.11700.pdf

https://github.com/chiehwangs/3d-gaussian-theory


https://github.com/MrNeRF/awesome-3D-gaussian-splatting


https://github.com/MrNeRF/gaussian-splatting-cuda