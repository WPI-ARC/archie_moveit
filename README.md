Archie Moveit
==========================

# Install

## on laptop side:

    cd $ROS_PACKACKAGE_PATH/src
    git clone 
    git clone ...
    catkin_make
    
## on PR2 side:

    cd $ROS_PACKACKAGE_PATH/src
    git clone 
    git clone ...
    catkin_make

# Run

## on laptop side:

### (1) Launch human tracker

    roslaunch openni2_launch openni2.launch
    rosrun person_tracker opencv_tracker
    rosrun person_tracker moveit_object_sender
    
### (2) Launch robot motion planning interface
    
    roslaunch pr2_moveit_generated moveit_rviz.launch

## on PR2 side:

    roslaunch archie_moveit move_group.launch 

------------------------------------------------

OR KINECT
==========================

MODES:
    (a) Recording (Listening)
    (b) Playback


# (a) Recording

### (i) Set options

Before one can begin recording, there are a few settings that must be edited in the class_runSensors.py file.  Namely:

    self.prob.SendCommand('SetCustomTracker 1')

This tells the orkinect plugin which kinect topic to subscribe to. In order to have more than 1 kinect, you must use the multi tracker.

    0 will use openni_tracker
    1 will use the custom openni_tracker_multi
    
    self.prob.SendCommand('SetNumKinect 1') #still need to call as 1 if using default tracker.

Sets the number of kinects to subscribe to.  This needs to be set to 1 even if using the original skeleton tracker

....
