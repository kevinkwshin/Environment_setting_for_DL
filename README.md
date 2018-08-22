# Install Tensorflow on Ubuntu (16.04)


## Requirements
- An NVIDIA GPU with a compute capability of 3.0 or higher.
- I'll be using a GTX 1050 Ti hooked up externally to a thinkpad T420s through the express card port Python installed.
- Ubuntu comes with python already installed but I will be using anaconda

## Overview
- Step 1: Update your GPU driver (should be higher than version 390)
- Step 2: Install the CUDA Toolkit version 9.0 (with all the patches)
- Step 3: Install CUDNN 7.0.5
- Step 4: Install Tensorflow GPU with pip
- Step 5: Test it!

### Step 1: Update your GPU driver

<pre><code>sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-390
</pre></code>

Reboot your computer. To verify the installation, open a terminal and run the following command
<pre><code>nvidia-smi</pre></code>

### Step 2: Install the CUDA Toolkit (9.0)
go to https://developer.nvidia.com/cuda-90-download-archive and download the toolkit for linux, x86_64, ubuntu, 16.04.

<pre><code>sudo dpkg -i cuda-repo-ubuntu1604_9.0.176-1_amd64.deb 
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
sudo apt-get update
sudo apt-get install cuda-9-0</pre></code>

open your .bashrc file with nano
<pre><code>sudo nano ~/.bashrc</pre></code>

go to the last line and add the following lines (this will set your PATH variable)
<pre><code>export PATH=/usr/local/cuda-9.0/bin${PATH:+:$PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}</pre></code>

### Step 3: Install CUDNN 7.0.5
go to https://developer.nvidia.com/cudnn

Select CUDNN 7.0.5 for CUDA 9.0, download the cuDNN v7.0.5 Library for Linux (tar file)

<pre><code>tar -xzvf cudnn-9.0-linux-x64-v7.tgz
sudo cp cuda/include/cudnn.h /usr/local/cuda/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*</pre></code>

### Step 4: pip install tensorflow-gpu
I will be using a conda environment for installing tensorflow

create a conda environment by using the following command
conda create -n tf python=3.6 pip
activate your environment using
source activate tf
run the following command to install tensorflow

pip install tensorflow-gpu==1.5

### Step 5: Test it!
run the following lines
<pre><code>import tensorflow as tf
hello = tf.constant('hello tensorflow')
with tf.Session() as sesh:
    sesh.run(hello)</pre></code>
