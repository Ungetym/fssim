Fork of [AMZ-Driverless/fssim](https://github.com/AMZ-Driverless/fssim) adapted to run under ROS melodic and Mint 19 (Ubuntu Bionic).

# General Instruction for ROS

## Installation of ROS on Mint 19 (based on Ubuntu 18.04 bionic):

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu bionic main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
sudo apt-get update
sudo apt-get install ros-melodic-desktop-full python-catkin-tools
```

## Other useful stuff:
Use tmux to subdivide your terminal window instead of opening multiple terminal windows or tabs.

# How to Run It in your Workspace
## Create ROS workspace via
```bash
mkdir my_ws_name
cd my_ws_name
mkdir src
cd src
```
## Clone this repository and update dependencies
```bash
git clone https://github.com/Ungetym/fssim.git
cd src/fssim
./update_dependencies.sh
```
## Build the project
```bash
cd ../../..
catkin_make -j1
```
Note: For some reason building using mutliple cores/threads might fail due to cross dependencies
## Source the workspace
```bash
source devel/setup.bash
```
# Example application
Launch the application using
```bash
roslaunch fssim auto_fssim.launch
```
Note: On the first startup, Gazebo tries to download models. If this fails and the screen remains black, download the models [here](https://bitbucket.org/osrf/gazebo_models) and place them in the .gazebo/models directory.

# For autonomous driving check the [AMZ-Driverless/fsd_skeleton fork](https://github.com/Ungetym/fsd_skeleton)
