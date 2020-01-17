# Lab 2 - RSECS4501(Spring2020)

This is the code used for lab 2 of the course Robotics for Software Engineers at the University of Virginia. The code contains a simple rocketship example in ROS. The rocket has a countdown, launches using command velocities, and has an abort function. The simple rocketship example is used to teach the basics of ROS. Please find the lab details in the website below

## Lab Webpage

Will update when webpage goes lives

## Prerequisites

We expect you to be running the virtual machine provided for this lab. The virtual machine can be downloaded [here](https://www.dropbox.com/s/s6zpud4ubuuy031/robotclass_base.ova?dl=1) and opened in Oracle's Virtual Box. If the virtual machine is unavailable, you can run this code on a Linux machine running Ubuntu 16.04. To install everything you need, you can do the following:

### Updating Linux
First, we need to update Linux and make sure all that it has all the latest packages. You can update the system using:

```bash
$ sudo apt-get update 
$ sudo apt-get dist-upgrade -y
```

Next, we want to install packages, programs, built tools and compilers which we are going to use:
```bash
$ sudo apt-get install git libeigen3-dev libxml2-utils cmake build-essential python-wstool protobuf-compiler libgoogle-glog-dev curl -y
```

### Installing a text editor

Install your favorite text editor. I recommend using vscode. You can install it by running the following commands:
```bash
$ curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
$ sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
$ sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
$ sudo apt update
$ sudo apt install code
```

You can then run vscode by searching for it in the search bar or by typing `code` in a terminal.

### Installing ROS

Next lets install ROS (For full details use: https://wiki.ros.org/kinetic/Installation/Ubuntu). However I have included the basics below. Note we are installing a couple of extra ROS packages.
```bash
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
$ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
$ sudo apt-get update
$ sudo apt-get install ros-kinetic-desktop-full ros-kinetic-libuvc-camera ros-kinetic-qt-create ros-kinetic-aruco ros-kinetic-mav-msgs python-catkin-tools -y
$ sudo rosdep init
$ rosdep update
```

Now lets add ROS to the bashrc file. Doing this allows you to access ROS from all terminals from now on
```bash
$ echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```