# Car control using turtlesim-teleop with keyboard along with laser-scan mapping

To use these packages you need ros-melodic. 
Add the 3 packages inside catkin/src/ directory.

----------------------------------------------------------------------------------------------------
### What does this project do?
Project contains a car with front and rear cameras and a laser in the front. A simple world has been
to demonstrate the working of all components. The car is controlled using turtlesim teleop. The laser
scan map is displayed in rviz. 

If you are just interested in running the packages skip to run the project section.

mybot_control package contains the configuration required for providing effort to left and right wheel 
hinge.

mybot_description contains the xml files for the bot.

mybot_gazebo contains the core logic of the project. The launch file of this package calls the launch 
files of the other two packages and they need not be launched explicitly. mybot_gazebo/src directory
contains the cpp file for capturing the laser scan points and making a map.

----------------------------------------------------------------------------------------------------
### To run the project:
Open terminal --> navigate to /cakin_ws 
Enter: catkin_make

In terminal enter: roslaunch mybot_gazebo mybot_world.launch
Open new terminal --> Enter: roslaunch mybot_gazebo assembler.launch
Open new terminal --> Enter: rosrun mybot_gazebo laser_assembler_service_caller
Open new terminal --> Enter: rosrun turtlesim turtle_teleop_key /turtle1/cmd_vel:=/mybot/cmd_vel 

