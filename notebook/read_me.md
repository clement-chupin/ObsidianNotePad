
# Installation :

### Install cuda 12.1

To speed up the computation, we recommend to use your GPU, you might already have cuda pre-installed, we recommend to use Cuda12.1 with pytorch2.1.1. To install cuda :
`Applications > Software & Updates > Additional Drivers > Select "Using NVIDIA driver metapackage from nvidia-driver-530 (proprietary)"`

### Install conda :
(refer to https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)

Download install installer script and execute it:
```bash
wget https://repo.anaconda.com/archive/Anaconda3-2023.09-0-Linux-x86_64.sh
bash Anaconda3-2023.09-0-Linux-x86_64.sh
```

### Install python environement :
```bash
conda env create -f environment.yml
```
# Execution :
### Source python and ROS environement :

```bash
conda activate py_ros
source ~/projects/tiara_ws/devel/setup.bash
```


### Generate data based on simulation environment :


```bash
roslaunch romea_furrow_training gen_data_furrow_all.launch
```


### Evaluate trajectory tracking :

```bash
roslaunch romea_furrow_training eval_furrow_all.launch.launch`
```



# Change ROS software

Ros is only present in `nodes` folder, if yout want to swap of ROS version or the entire software, adapt the code in `nodes` folder.



# Software used : 

tree describes the dependencies between libraries :
```bash
Ubuntu=20.04
	Ros-noetic
		Python=3.8
torch=2.1.1
	cuda version=12.1
		nvidia-driver=530
	numpy=1.20.0
```


# Tips and tricks :


## Check software version :

### In bash :

```bash
python --version
pip show torch
```

### In python file :

Python version :

```python
import sys
print("Python version")
print (sys.version)
print("Version info.")
print (sys.version_info)
```

Package version :

```python
import torch
torch.__version__
```
