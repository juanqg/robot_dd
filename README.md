# Differential Drive 4wd Robot (robot_dd)
URDF File and Model of Four-Wheeled Mobile Robot in ROS Noetic.

Here you will find the basic details to define a simple Robot model (URDF) to jump start a ROS development.

## Setting the Environment
You need to have ROS Noetic installed follow [this guide](http://wiki.ros.org/noetic/Installation/Ubuntu)

Besides the main Noetic version you also need to have URDF and RVIZ to be able to compile and visualize your model.

***You can install URDF and RVIZ with the following commands, open a terminal and enter:***
```
sudo apt-get update && apt-get upgrade -y
sudo apt-get install ros-noetic-rviz
sudo apt-get install ros-noetic-urdf
sudo apt-get install liburdfdom-tools
sudo apt-get install ros-noetic-xacro
```

>[!Test your environment]
>Make sure your environment is properly sourced by testing with the following commands.

***ROS Console***
Open a terminal and enter:
```
roscore
```

***On another terminal you can now test RVIZ***
```
rosrun rviz rviz
```

Once you have your enviroment set, you may clone this repository and set the source for ROS:
```
source $PWD/devel/setub.bash
echo $ROS_PACKAGE_PATH
```

The development packages were generated using the following command on the src folder:
```
catkin_create_pkg robot_model_pkg roscpp tf2 geometry_msgs urdf rviz joint_state_publisher_gui
```

> Below the dependencies for this project:
* roscpp - cpp and ROS
* tf2 - Lets the user keep track of multiple coordinate frames over time
* geometry_msgs - messages for common geometry primitives such as points, vectors and poses.
* urdf - C++ parser for URDF package
* rviz - RVIZ
* joint_state_publisher_gui - Contains a GUI tool for setting and publishing joint state values for a given URDF.

Once the environment and packages references are created, you can create the main folders references for ROS URDF and Launch, you've noticed that this model was named **"robot_model_pkg"** you could use any name you want at the catkin_create_pkg sentence described above.

The **"robot_model_pkg"** folder is the main robot model folder besides the different definitions and references required by ROS to generate your model you may also save your RVIZ settings to easily jump back in right where you left it. 

The main folders to start the development inside ***robot_model_pkg***:
```
mkdir urdf
mkdir launch
```

The definition is in the urdf folder and the execution parameters are in the launch respectively.

This will give you an idea of the design used for the frame:

![This is an image to aid in the file definition](/assets/4wd_design.png)


Once you have your definition and launch file created, you can open a terminal in your main folder location and compile your model:
```
catkin_make
```

After the compilation ends, you may launch ROS with
```
roscore
```

Open another terminal and launch your model with:
```
roslaunch robot_model_pkg robot.launch
```

This is an screenshot of your model in RVIZ:

![This is your model](/assets/rviz.png)

