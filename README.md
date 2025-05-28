# 6d-pose-extras-
## Setup Instructions

> **Note:** This setup is intended to run natively on **Ubuntu**. Running it inside a virtual machine is **not recommended**, as it may lead to compatibility issues or degraded performance.

---

### CUDA Toolkit Installation

```bash
sudo apt update
sudo apt install -y nvidia-cuda-toolkit

## 2. Intel RealSense SDK Installation

To install the Intel RealSense SDK on Ubuntu, follow these steps:

```bash
# Authenticate and add the Intel RealSense APT repository
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key F6B0FC61
sudo add-apt-repository "deb http://realsense-hw-public.s3.amazonaws.com/Debian/apt-repo $(lsb_release -cs) main"

# Update the package list
sudo apt update

# Install the required RealSense packages
sudo apt install librealsense2-dkms librealsense2-utils librealsense2-dev

Instead of running:
```bash
sudo apt install ros-<ROS_DISTRO>-librealsense2*

## 3. Important Notes and CUDA Environment Setup
export CUDA_HOME=/usr/local/cuda-12.2
export PATH=$CUDA_HOME/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=$CUDA_HOME/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

## 4. Clone FoundationPose Repository

Clone the official [FoundationPose](https://github.com/NVlabs/FoundationPose) repository into a folder named `FoundationPose`:

```bash
git clone https://github.com/NVlabs/FoundationPose.git FoundationPose

## 5. Build with Correct Path

When building the `FoundationPoseROS2` repository, make sure you set the correct CUDA path **without any trailing characters like `~`**.

### Incorrect Command

```bash
cd FoundationPoseROS2 && export PATH=/usr/local/<YOUR_cuda-12.X_VERSION>/bin${PATH:+:${PATH}}~ && bash build_all_conda.sh
### Correct Command

```bash
cd FoundationPoseROS2 && export PATH=/usr/local/<YOUR_cuda-12.X_VERSION>/bin${PATH:+:${PATH}} && bash build_all_conda.sh

## 6. Install Python Dependency

Before running the code, make sure to install the required Python dependency:

```bash
pip install ruamel.yaml




