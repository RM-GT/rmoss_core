# Installation Guide

Due to the limitation of JetPack, we can only install Ubuntu 20.04. To install this repo, you need to compile the ROS 2 Humble distribution. The tutorial is located here [Installing Humble from Source](https://docs.ros.org/en/humble/Installation/Alternatives/Ubuntu-Development-Setup.html).

After installation create a work space with the following 3 repositories:
```bash
mkdir ~/your_workspace/src
cd ~/your_workspace/src
git clone https://github.com/RM-GT/rmoss_core.git -b humble-20.04
git clone https://github.com/robomaster-oss/rmoss_interfaces.git -b humble
git clone https://github.com/ros-perception/vision_opencv.git -b humble
cd ..
rosdep install -y -r -q --from-paths src --ignore-src --rosdistro humble
colcon build --symlink-install

```
We are installing `cv_bridge` from source since there is no prebuilt version of it for humble on ubuntu 20.04.
