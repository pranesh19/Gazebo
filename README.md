# The Ultimate Gazebo Workspace - rhinoceROS 🦏 #

## Contents: 

[ros_service](https://github.com/leander-dsouza/Gazebo/tree/master/rhinoceROS/src/ros_service) - A global planner service package. 

<img src="https://user-images.githubusercontent.com/45683974/77653435-ad81da00-6f95-11ea-88cb-1e7cbcd500f9.gif" width="900" height="500">

[atreus Ω](https://github.com/leander-dsouza/Gazebo/tree/master/rhinoceROS/src/atreus) - A package containing a mutlipurpose  four- wheeled differential drive robot equipped with sensors such as IntelRealSense R200 Depth Camera, LiDAR, Ultrasonics, GPS, IMU, Magnetometer and a pair of cameras.

#### Functionality:

* Obstacle Avoidance with soft turning using pcl processing (passthrough + voxel + ransac + euclidean clustering + centroidal analysis).

* Detection of slope angle and ditch depth by using a sonar panel.

* Dynamic traversal using GPS and IMU to reach desired location.

* Ability of localisation by using 2 independent EKFs.

* Teleoperation with respect to waypoints/time by path smoothening.

* Alvar Gate Traversal.

* Tennis Ball Detection.


<img src="https://user-images.githubusercontent.com/45683974/77582804-fab66b00-6f05-11ea-915e-847d5defb0b9.gif" width="900" height="500">

Installation
------------

Run a catkin make in the rhinoceROS folder:

    catkin_make

Source the bash script in the devel folder in rhinoceROS:

    source ~/Gazebo/rhinoceROS/devel/setup.bash
    
For basic bot simulation:

    roslaunch atreus spawn_my_bot.launch


Errors
------------
-- 1) Run the following command if the traffic light does not glow red: 

    sudo apt-get install ros-melodic-gazebo-* && sudo apt-get install gazebo9 && sudo apt-get install libgazebo9* && sudo apt-get --reinstall install libignition-math4 && sudo apt-get --reinstall install libignition-math4-dev && sudo apt-get upgrade
    
-- 2) Run the following command if the GPS and IMU sensors values are not seen through a rostopic list: 

    sudo apt-get install ros-melodic-hector-gazebo-plugins

-- 3) In case if you don't have the ROS package ar track alvar: 

    sudo apt-get install ros-melodic-ar-track-alvar
