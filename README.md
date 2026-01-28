# 📍 Where Am I? — Mobile Robot Localization Using AMCL (ROS Noetic)

## Project Overview

**Where Am I?** is a ROS-based localization project that demonstrates accurate localization of a mobile robot within a known map using the **Adaptive Monte Carlo Localization (AMCL)** algorithm. The robot operates inside a Gazebo simulation environment and uses laser scan data together with a pre-generated occupancy grid map to estimate its pose.

This project integrates:
- Gazebo simulation  
- ROS Navigation Stack  
- AMCL localization  
- RViz visualization  
- Keyboard teleoperation  

---
![Localization in RViz](rviz.png)

##  System Requirements

- Ubuntu 20.04  
- ROS Noetic  
- Gazebo  
- Git  

---


## Create Catkin Workspace

```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```
## Clone Repository

```bash
cd ~/catkin_ws/src
git clone https://github.com/jamal2134/Where-am-i2030.git
```
## Build Workspace

```bash
catkin_make
source devel/setup.bash
```

## Install Navigation Stack

```bash
sudo apt install ros-noetic-navigation ros-noetic-map-server ros-noetic-amcl ros-noetic-move-base
```


## Map Setup

To generate an occupancy grid map, follow the instructions provided in:
```bash
https://github.com/JZX-MY/pgm_map_creator
```
After generating the map, place the .pgm and .yaml files inside:
```bash
location/maps/
```


# Install Teleop Package
1. Clone teleop package:
```bash
cd /home/workspace/catkin_ws/src
git clone https://github.com/ros-teleop/teleop_twist_keyboard
```
2. Build:

```bash
cd ..
catkin_make
source devel/setup.bash
```

3.Run teleoperation:
```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py

```


# Running the Project
- Terminal 1 — Launch Gazebo World
```bash
roslaunch my_robot world.launch
```
- Terminal 2 — Launch Localization (AMCL)
```bash
roslaunch location amcl.launch
```
- Terminal 3 — Keyboard Control
```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```







