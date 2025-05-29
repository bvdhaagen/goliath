# goliath
Golitah is a semi industrial 6 dof robot arm  
![Screenshot from 2025-05-29 22-37-02](https://github.com/user-attachments/assets/6f8a0ce4-88ff-46e2-95ce-c0b8a4a56aea)

# Goliath installation steps
install ros humble >>  https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html

# install ros2 control and ros2 controllers 

sudo apt install ros-humble-ros2_control* 

# install moveit and the repo's for humble 

detailed instructions will follow

# create a workspace and clone the goliath package and build it 

mkdir -p goliath_ws/src   

cd goliath/src

git clone https://github.com/bvdhaagen/goliath.git

cd ..

rosdep init 

rosdep update

rosdep install --from-paths src -y --ignore-src

colcon build --symlink-install 

# add your build to the source 
source install/setup.bash

![Screenshot from 2025-05-29 22-33-48](https://github.com/user-attachments/assets/3b7c2b53-0783-415c-84df-7c2407b20006)



# Launch the Goliath ros2_control simulation

instructions will follow soon

# Launch Goliath ros2_control on real robot 
sudo chmod 666 /dev/ttyACM0 && sudo chmod +x /dev/ttyACM0 

ros2 launch goliath_controller goliath_controller.launch.py 
- testline :   ros2 topic pub /position_controller/commands std_msgs/msg/Float64MultiArray '{data: [0.0, -0.40, 1.0, 0.0, 0.5, 0.0]}' --once 

# Lauch Goliath with moveit in simulation 

instructions will follow soon

# Launch Goliath with moveit on real robot

ros2 launch goliath_moveit demo.launch.py 
