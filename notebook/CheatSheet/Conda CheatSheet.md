gitrm -rf anaconda3
rm -rf ~/anaconda3
rm -rf ~/opt/anaconda3


wget https://repo.anaconda.com/archive/Anaconda3-2023.09-0-Linux-x86_64.sh

bash Anaconda3-2023.09-0-Linux-x86_64.sh


conda install python=3.5.0
conda update --all

conda create -n myenv python=3.8 pip 
conda env create --file environment.yml 
conda remove --name py_ros --all
conda env export > environment.yml
conda activate py_ros
conda deactivate

pip install "git+https://github.com/isl-org/Open3D.git"


conda install -c open3d-admin open3d







```
conda create --name sugar -y python=3.9
conda activate sugar
conda install pytorch==2.0.1 torchvision==0.15.2 torchaudio==2.0.2 pytorch-cuda=11.8 -c pytorch -c nvidia
conda install -c fvcore -c iopath -c conda-forge fvcore iopath
conda install pytorch3d==0.7.4 -c pytorch3d
conda install -c plotly plotly
conda install -c conda-forge rich
conda install -c conda-forge plyfile==0.8.1
conda install -c conda-forge jupyterlab
conda install -c conda-forge nodejs
conda install -c conda-forge ipywidgets
conda install -c open3d-admin open3d
pip install --upgrade PyMCubes
```













conda update -n base -c defaults conda
conda update -n base conda
conda install -n base conda-libmamba-solver
conda config --set solver libmamba



conda install --rev 0  # this will revert your environment to its default state, removing all dependencies installed there
conda update conda # This will install the latest conda



conda create -n sugar python=3.9 pip torch=2.0.1 torchaudio=2.0.2 torchvision=0.15.2
conda activate sugar
pip install torch==2.0.1
pip install pytorch3d
conda install pytorch3d



sudo conda create -n base
sudo conda update -n base conda
sudo conda install -n base conda-libmamba-solver
conda config --set solver libmamba
