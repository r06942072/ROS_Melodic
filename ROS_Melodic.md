# ROS_Melodic
### Ubuntu install of ROS Melodic  
http://wiki.ros.org/melodic/Installation/Ubuntu

*Install Desktop-Full:  ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators and 2D/3D perception  
```sudo apt install ros-melodic-desktop-full```

*Install Dependencies  
```sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential```

*check ROS related env var  
```env | grep ROS```

### catckin workspace
http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment

```source devel/setup.bash```

*make sure that ROS_PACKAGE_PATH include my path  
```echo $ROS_PACKAGE_PATH```

### Creating a ROS Package
```sudo apt-get install ros-melodic-ros-tutorials```
  
*catkin_create_pkg <package_name> [depend1] [depend2] [depend3]   
```cd ~/catkin_ws/src```  
```catkin_create_pkg beginner std_msgs rospy roscpp```

*Building a catkin workspace  
```
cd ~/catkin_ws
catkin_make
```
 
*source the generated setup file, after doing this, we can see the package by command ```rospack```  
```. ~/catkin_ws/devel/setup.bash```  

*check first-order dependencies of package  
*rospack depends1 [package_name]  
```rospack depends1 beginner``` 

*check all nested dependencies  
```rospack depends beginner```  

### Building a ROS Package ???  

### ROS Nodes
http://wiki.ros.org/ROS/Tutorials/UnderstandingNodes

```roscore```  
```rosnode list```  
```rosnode info /rosout```  

*rosrun [package_name] [node_name]  
```rosrun turtlesim turtlesim_node```  

### ROS Topics  
Two nodes are running: turtlesim_node and turtle_teleop_key node.  
They are communicating with each other over a ROS Topic.  
```roscore```  
```rosrun turtlesim turtlesim_node```  ( subscriber )  
```rosrun turtlesim turtle_teleop_key```  ( publisher )  

*using rqt_graph  
```rosrun rqt_graph rqt_graph```  

*show the information about ROS topics.  
```rostopic echo /turtle1/cmd_vel```

*returns a list of all topics currently subscribed to and published.  
```rostopic list -v```  

*draw coordinate graph  
```rosrun rqt_plot rqt_plot```  

### ROS Services  
Services allow nodes to send a request and receive a response  
```rosservice list```  

*check what arguments need to take for specific call  
*rosservice type [service]  
```rosservice type /clear```  

*clean the path that turtle has run  
*rosservice call [service] [args]  
```rosservice call /clear```  

*spawn a new turtle, turtle2  
```rosservice type /spawn | rossrv show```  
```rosservice call /spawn 2 2 0.2 "turtle2"```  

*using rosparam  
rosparam allows you to store and manipulate data on the ROS Parameter Server  
```rosparam list```  

*change background color  
```rosparam set /background_r 150```
*call the clear service for the parameter change to take effect  
```rosservice call /clear```  

```rosparam get /```  

### Using roslaunch  
```roscore```  
roslaunch starts nodes as defined in a launch file.  
*In project **beginner**, create a folder named launch  
```cd ~/catkin_ws/src/beginner```  
```mkdir launch```  
```cd launch```  

*create a launch file  
*look in the code, find out that turtlesim2 to mimic turtlesim1   
```vim turtlemimic.launch```  

*launch it  
```roslaunch beginner turtlemimic.launch```
???   

### Using rosed to edit files in ROS   
rosed [package_name] [filename]  

### Creating a ROS msg and srv  
```
roscd beginner
mkdir msg
echo "int64 num" > msg/Num.msg
```







  

