# Roomba ROS2 #

ROS2 packages for the [Roomba-RPi project](https://github.com/process1183/roomba-rpi).


## Dependencies ##

| Package Name | Description | URL |
| ------------ | ----------- | --- |
| `ros2_bno055` | ROS2 node for the Bosch BNO055 IMU | [github.com/process1183/ros2_bno055](https://github.com/process1183/ros2_bno055) |
| `create_driver` | ROS driver for iRobot Create 1 and 2. | [github.com/AutonomyLab/create_robot](https://github.com/AutonomyLab/create_robot/tree/foxy) |
| `libcreate` | C++ library for interfacing with iRobot's Create 1 and 2 as well as most models of Roomba. | [github.com/AutonomyLab/libcreate](https://github.com/AutonomyLab/libcreate) |


## Installation ##

__1.__ Create a ROS2 workspace and clone the required repos:


```
mkdir -p ~/roomba_ws/src
cd ~/roomba_ws

wget https://raw.githubusercontent.com/process1183/roomba-ros2/main/roomba_ros2.repos

vcs import src < roomba_ros2.repos
```


__2.__ Source the ROS2 setup file. Adjust as needed to match your ROS2 installation location.


```
. /opt/ros2_galactic/install/local_setup.bash
```


__3.__ Install Dependencies:


```
cd ~/roomba_ws

rosdep install -y -r --from-paths src --ignore-src
```


__4.__ Build:


```
colcon build --symlink-install
```


__5.__ Run:

```
. ~/roomba_ws/install/local_setup.bash

ros2 launch roomba_bringup roomba.launch.py
```
