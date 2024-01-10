
sudo lshw -C display

sudo /usr/local/cuda-11.7/bin/cuda-uninstaller 
sudo apt-get purge nvidia*
sudo apt-get autoremove

https://developer.nvidia.com/cuda-toolkit-archive

wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run
sudo sh cuda_11.8.0_520.61.05_linux.run



sudo apt install cuda-11.2




ls /usr/local  


conda install -c "nvidia/label/cuda-11.8.0" cuda-toolkit
11.8

https://developer.nvidia.com/rdp/cudnn-archive

```bash
sudo gedit ~./bashrc
export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}  
export LD_LIBRARY_PATH="/usr/local/cuda/lib64:/usr/local/cuda-10.1/lib64:/usr/local/cuda-11/lib64:/usr/local/cuda-11.1/lib64:/usr/local/cuda-11.2/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}"#make sure you add your cuda-X.x lib64 paths
```


REBOOT YOUR COMPUTER