# ROS-navigation-guide
***Note: This guide is a follow up for the previous [repo](https://github.com/MajeedReact/ROS_Simulation_guide), TurtleBot3 World is used to creat a map. The same Gazebo environment will be used for Navigation.***

# Launch simulation world

1. Open a terminal and run the following: \
   `export TURTLEBOT3_MODEL=burger` \
   `roslaunch turtlebot3_gazebo turtlebot3_world.launch` 
   
    *Use the proper keyword among `burger`, `waffle`, `waffle_pi` for the TURTLEBOT3_MODEL parameter*
    
# Run the navigation node

1. Open a new terminal with `CTRL` + `Alt` + `T`
2. Choose a model and run the navigation node: \
    `export TURTLEBOT3_MODEL=burger` \
    `roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml` \
    Where $HOME is the directory that have the map image in
    
3. After running the commands above you'll have a similar result to this: 
![1](https://user-images.githubusercontent.com/53359513/125358808-1307fe80-e372-11eb-9acf-1e8888fc63c5.jpg)

# Estimate Initial Pose

Initial Pose Estimation must be performed before running the navigation.

1. Click the 2D Pose Estimate button in the RViz menu.
![2](https://emanual.robotis.com/assets/images/platform/turtlebot3/navigation/2d_pose_button.png)

2. Click on the map where the actual robot is located and drag the large green arrow toward the direction where the robot is facing.
3. Repeat step 1 and 2 until the LDS sensor data is overlayed on the saved map.
4. Launch keyboard teleoperation node to precisely locate the robot on the map.
   `roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`.
   
  5. Move the robot back and forth a bit to collect the surrounding environment information and narrow down the estimated location of the TurtleBot3 on the map which is displayed with tiny green arrows.
![2](https://user-images.githubusercontent.com/53359513/125360253-49467d80-e374-11eb-8b88-8fb6d14b27b0.jpg)

6. Terminate the keyboard teleoperation node by entering `ctrl` + `C`



# Set navigation goal

1. Click the `2D Nav Goal` button in the RViz menu.
![3](https://emanual.robotis.com/assets/images/platform/turtlebot3/navigation/2d_nav_goal_button.png)

2. Click on the map to set the destination of the robot and drag the purple arrow


https://user-images.githubusercontent.com/53359513/125362276-4bf6a200-e377-11eb-9f8c-c66055be375c.mp4

The robot will automatically move by itself and avoid obstacles to reach the coordinates.

