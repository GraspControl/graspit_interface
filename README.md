graspit_interface
=================

This plugin exposes a ROS interface for the GraspIt! simulator. Our main purpose for writing
this plugin was to give GraspIt! more exposure to the ROS community and make it easier to
get started planning grasps with GraspIt! You can interact with this interface through a
variety of ROS services and action servers.

This repo is currently in **active development**, and we plan on exposing a majority of GraspIt!'s
functionality to ROS, including all of GraspIt!'s planning capabilities. If you have any specific
features you'd like us to work on, let us know by submitting a new issue. If you feel comfortable
with GraspIt! and would like to help us get this done quicker, feel free to submit a pull request!

To see how a client interacts with this interface, check out our python
[graspit_commander](https://github.com/CURG/graspit_commander).

If you've got your own implementation in another language, let us know and we'll link to it here!

Dependencies:
-------------
- [ros](http://wiki.ros.org/indigo/Installation) (ROS Indigio is our officially supported
development flavor)
- [graspit](https://github.com/graspit-simulator/graspit) and
[graspit-ros](https://github.com/graspit-simulator/graspit-ros)
(*Note: Check out how we set this up [here](#graspit)*

Setup:
------
###ROS:
If you don't already have ROS set up, follow the tutorial [here](http://wiki.ros.org/indigo/Installation).

###Your workspace:
We like to keep everything set up within a single ROS (catkin) workspace to keep things simple.
If you're new to ROS or GraspIt!, it may be useful to set up your workspace in the same way so
you can follow our tutorials more easily. 

```
mkdir -p graspit_ros_ws/src
cd graspit_ros_ws/src

source /opt/ros/indigo/setup.bash
catkin_init_workspace . 
```

###GraspIt!:
```
git clone git@github.com:CURG/graspit_interface.git
git clone git@github.com:CURG/graspit_commander.git
git clone git@github.com:graspit-simulator/graspit-ros.git
cd graspit-ros
git submodule init
git submodule update
```
*Note: You only need to clone ```graspit_commander``` if you want to use our python client*

###Building
From the root of your catkin workspace (above the src directory) run:
```
catkin_make
```
*Note: you will need to `source /opt/ros/indigo/setup.bash` if you haven't already
before running catkin_make* 


Run the interface!:
-------
```
source devel/setup.bash
roslaunch graspit_interface graspit_interface.launch
```
