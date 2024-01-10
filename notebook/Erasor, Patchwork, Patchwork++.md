*Mastering the RandSaC and PCA by iterative loss function*


## ERASOR: Egocentric Ratio of Pseudo : Occupancy-based Dynamic Object Removal for

Static 3D Point Cloud Map Building
https://arxiv.org/pdf/2103.04316.pdf


##### Scan Ratio Test :
*Compare the map regstered to current scan to detect dynamics objects*
![[Pasted image 20231211104859.png]]



##### R-GPF : Region-wise Ground Plane Fitting : 
*fit a plane by region by RANSAC+PCA*

![[Pasted image 20231211100829.png]]




## Patchwork: Concentric Zone-based Region-wise Ground Segmentation with Ground Likelihood Estimation Using a 3D LiDAR Sensor
https://arxiv.org/pdf/2108.05560.pdf



##### CZM : Concentric Zone Mode :
*split polar with uniform density by tiles*

![[Pasted image 20231211111838.png]]

##### GLE : Ground Likelihood Estimation :
*Define loss function of ground, based on uprightness, elevation,
and flatness*


![[Pasted image 20231211112359.png]]



## Patchwork++: Fast and Robust Ground Segmentation Solving Partial Under-Segmentation Using 3D Point Cloud
https://arxiv.org/pdf/2207.11919.pdf


![[Pasted image 20231211113419.png]]




##### RNR : Reflected Noise Removal
*remove reflect ghost underground points, by angular attack of the ground (close points of the sensor), and low intensities filtering*

"Consequently, RNR efficiently removes
noise points with unrealistically large negative z values with
a negligible loss of actual ground points. In particular, hnoise
is self-updated by A-GLE"


##### R-VPF : Region-wise Vertical Plane Fitting

*R-GPF with vertical plane rejecting, similar to GLE*

"To this end, R-VPF is proposed, allowing R-GPF to esti-
mate more accurate ground planes by rejecting dominant and
vertical points for preprocessing within a bin"



##### A-GLE : Adaptive Ground Likelihood Estimation
*classical GLE but woth global adaptative threshold in despite than absolute threshold, mean + a.var*







##### TGR : Temporal Ground Revert


"For example, rough terrains
with grass sometimes have higher en and fn than the self-
updated parameters. This is because A-GLE updates its
parameters based on all values over time. Accordingly, this
makes A-GLE play a role as a low-pass filter, which makes
it difficult to estimate the bin as ground when fn becomes
temporarily large"

![[Pasted image 20231211171330.png]]


if points rejected, global time var < local time var, points are ground






Octomap, based on octrees :


![[Pasted image 20231211103238.png]]

