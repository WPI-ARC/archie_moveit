Archie Moveit
==========================

# Install

In order to 
## on laptop side:
Go to src folder in catkin workspace and download required packages:
    
    sudo apt-get install ros-groovy-rviz
    git clone git@github.com:ros-drivers/openni2_launch.git
    git clone https://github.com/WPI-ARC/person_tracker.git
    git clone https://github.com/WPI-ARC/pr2_moveit_generated.git

Go back one level and make all downloaded packages:
    
    cd ..
    catkin_make
    
## on PR2 side:
Go to catkin workspace and download archie_moveit package.

    git clone https://github.com/WPI-ARC/archie_moveit.git
    git clone https://github.com/WPI-ARC/moveit_core.git
    git clone https://github.com/WPI-ARC/moveit_ros.git

Go back one level and make the package:

    catkin_make

# Run

## on PR2 side:

Run the launch file on PR2 side before running launch files on laptop side.

    roslaunch archie_moveit move_group.launch 

## on laptop side:

### (1) Launch human tracker

    roslaunch openni2_launch openni2.launch
    rosrun person_tracker opencv_tracker
    rosrun person_tracker moveit_object_sender
    
### (2) Launch moveit motion planning interface
    
    roslaunch pr2_moveit_generated moveit_rviz.launch
