# Deep Learning Part

### Install Ubuntu Dependencies
First update the system
```shell
sudo apt-get update
sudo apt-get upgrade
```
Then install development tools, image & video I/O libraries, GUI packages, optimization libraries, and other packages:
```shell
sudo apt-get install build-essential cmake unzip pkg-config
sudo apt-get install libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev
sudo apt-get install libjpeg-dev libpng-dev libtiff-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install libgtk-3-dev
sudo apt-get install libopenblas-dev libatlas-base-dev liblapack-dev gfortran
sudo apt-get install libhdf5-serial-dev
sudo apt-get install python3-dev python3-tk python-imaging-tk
```
CUDA 9 requires gcc v6 but Ubuntu 18.04 ships with gcc v7 so we need to install gcc and g++ v6  
Not sure if needed since CUDA is now with newer vision 10.1
```shell
sudo apt-get install gcc-6 g++-6
```
### Install latest NVIDIA drivers
Download the driver from the [homepage](https://www.nvidia.com/download/driverResults.aspx/138279/en-us) (410.57 at the moment).
```shell
chmod +x Downloads/NVIDIA-Linux-x86_64–410.57.run
sudo Downloads/NVIDIA-Linux-x86_64–410.57.run --no-x-check
```
`Continue installation` -> `No` for registering the kernel module sources with DKMS -> `Yes` for install Nvidia 32-bit compatible libraries -> `No` for automatically updating X configuration file

Reboot after the successful installation.
```shell
nvidia-smi
nvidia-settings
```
An example
```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 410.57                 Driver Version: 410.57                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  GeForce RTX 20..    Off  | 00000000:01:00.0  On |                  N/A |
| 21%   30C    P5    16W / 215W |    370MiB /  7949MiB |      1%      Default |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|    0      1196      G   /usr/lib/xorg/Xorg                            18MiB |
|    0      1230      G   /usr/bin/gnome-shell                          57MiB |
|    0      1508      G   /usr/lib/xorg/Xorg                           135MiB |
|    0      1641      G   /usr/bin/gnome-shell                         150MiB |
|    0     19091      G   /usr/lib/firefox/firefox                       6MiB |
+-----------------------------------------------------------------------------+
```

**Refer**: 
- [Ubuntu 18.04: Install TensorFlow and Keras for Deep Learning](https://www.pyimagesearch.com/2019/01/30/ubuntu-18-04-install-tensorflow-and-keras-for-deep-learning/)
- [How to install Nvidia drivers and cuda-10.0 for RTX 2080 Ti GPU on Ubuntu-16.04/18.04](https://medium.com/@avinchintha/how-to-install-nvidia-drivers-and-cuda-10-0-for-rtx-2080-ti-gpu-on-ubuntu-16-04-18-04-ce32e4edf1c0)

