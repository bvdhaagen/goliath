# goliath
Golitah is a semi industrial 6 dof robot arm  

Goliath installation steps
install ros humble >>  https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html

install ros2 control and ros2 controllers 

sudo apt install ros-humble-ros2_control* 

install moveit and the repo's for humble 

create a workspace and clone the goliath package into it 

mkdir -p goliath_ws/src   install dependancies    build the controllers 
cd goliath/src
git clone https://github.com/bvdhaagen/goliath.git
cd ..
rosdep init 
rosdep update
rosdep install --from-paths src -y --ignore-src
colcon build --symlink-install 

add your build to the source 
source install/setup.bash

Launch the Goliath ros2_control simulation

Launch Goliath ros2_control on real robot 

Lauch Goliath with moveit in simulation 

Launch Goliath with moveit on real robot
