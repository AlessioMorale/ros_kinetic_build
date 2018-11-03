- [Introduction](#introduction)
- [Installing prerequisites](#installing-prerequisites)

## Introduction
This repository contains a modified .rosinstall file and scripts to build ros-kinetic-desktop-full on bionic.

## Installing prerequisites
Beefore proceding to run ./build you need to install the following prerequisites .

The first step is to add the Melodic repository as it will provide the dependencies for some base tools. This step is very important to prevent the ROS packages included in Bionic to mess up with the rest of the installation. 

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116

sudo apt update
```

Then install a few additional requisites and initialize rosdep
```
sudo apt-get install python-rosdep python-rosinstall-generator python-wstool python-rosinstall build-essential

sudo rosdep init

rosdep update
```

Now you can issue ./build and wait until it completes to fetch and compile everything (i warn you, it will take quite a bit of time).



