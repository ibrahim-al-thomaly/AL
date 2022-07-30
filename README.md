# installROS
Install Robot Operating System (ROS) Melodic on NVIDIA Jetson Developer Kits

These scripts will install Robot Operating System (ROS) Melodic on the NVIDIA Jetson Developer Kits. 

Jetson Nano, Jetson AGX Xavier, Jetson Xavier NX, Jetson TX2, Jetson TX1

The script is based on the Ubuntu ARM install of ROS Melodic: http://wiki.ros.org/melodic/Installation/Ubuntu

Maintainer of ARM builds for ROS is http://answers.ros.org/users/1034/ahendrix/

There are two scripts:

<strong>installROS.sh</strong>
<pre>
Usage: ./installROS.sh  [[-p package] | [-h]]
 -p | --package &lt;packagename&gt;  ROS package to install
                               Multiple Usage allowed
                               The first package should be a base package. One of the following:
                                 ros-melodic-ros-base
                                 ros-melodic-desktop
                                 ros-melodic-desktop-full.
 </pre>
 
Default is ros-melodic-ros-base if no packages are specified.

Example Usage:

`$ ./installROS.sh -p ros-melodic-desktop -p ros-melodic-rgbd-launch`

This script installs a baseline ROS environment. There are several tasks:

* Enable repositories universe, multiverse, and restricted
* Adds the ROS sources list
* Sets the needed keys
* Loads specified ROS packages, defaults to ros-melodic-base-ros if none specified
* Initializes rosdep
* Sets up `ROS_MASTER_URI` and `ROS_IP` in the `~/.bashrc` file