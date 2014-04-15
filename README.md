on laptop side:
roslaunch openni2_launch openni2.launch
rosrun person_tracker opencv_tracker
rosrun person_tracker moveit_object_sender
roslaunch pr2_moveit_generated moveit_rviz.launch

on PR2 side:
roslaunch archie_moveit move_group.launch 

