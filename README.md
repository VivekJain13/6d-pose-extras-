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

