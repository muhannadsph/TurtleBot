
# Task 5: TurtleBot3 
In this task we need to install TurtleBot3 using the quick start quide to download it on ROS system.
At first we will need to open the ROBOTIS e-Manual then dynamixel system and choose TurtleBot3 then we will choose the version of ROS that we have on virtual box, I choose ROS Noetic.

## Website
https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/#pc-setup









 
## Installation steps

#### 1. Download and Install Ubuntu on PC
 At the beginning it's requested to download ubuntu and Ros on the PC, but we already did that in the pervious tasks.

#### 2. Install ROS on Remote PC
Open the terminal 
```bash
sudo apt update
```
```bash
sudo apt upgrade
```
```bash
wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools
```
```bash
chmod 755 ./install_ros_noetic.sh 
```
```bash
bash ./install_ros_noetic.sh
```
#### 3. Install Dependent ROS Packages
```bash 
sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy
ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc
ros-noetic-rgbd-launch ros-noetic-rosserial-arduino
ros-noetic-rosserial-python ros-noetic-rosserial-client
ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server
ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro
ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz
ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```

#### 4. Install TurtleBot3 Packages
```bash 
 sudo apt install ros-noetic-dynamixel-sdk
  ```
```bash
sudo apt install ros-noetic-turtlebot3-msgs
```
```bash
 sudo apt install ros-noetic-turtlebot3
 ```
#### 5. Simulation
#### 5.1 Gazebo simulation
The turtlebot3 and turtlebot3 msgs packages are required as requirements for the TurtleBot3 Simulation Package.
The Simulation cannot be launched without these necessary precursor packages.
If you did not install the required and dependent packages.
```bash
cd ~/catkin_ws/src/ 
```
```bash
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git 
```
```bash
cd ~/catkin_ws && catkin_make
```
To launch simulation world there are three simulation environments that are prepared for TurtleBot3. We can select on of these environments to launch Gazebo.

- burger 
- waffle
- house

```bash
export TURTLEBOT3_MODEL=waffle
```
 ```bash
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
```bash
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

#### 5.2 SLAM simulation

Launch Simulation World
```bash
export TURTLEBOT3_MODEL=waffle 
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
Run SLAM Node
```bash
export TURTLEBOT3_MODEL=waffle 
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
Run Teleoperation Node
```bash
export TURTLEBOT3_MODEL=waffle
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
```bash
source ~/.bashrc
```

#### Screenshot
![](https://github.com/BatolG/AI-Task-5/blob/main/task_51.jpg)
