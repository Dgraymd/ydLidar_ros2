1- install ROS2
2- create workspace 
mkdir -p ros2_ws/src
3- download and install YDLidar SDK
3_1 install CMake
sudo apt install cmake pkg-config
sudo apt-get install python swig
sudo apt-get install python-pip
3_2 Build YDLidar-SDK
git clone https://github.com/YDLIDAR/YDLidar-SDK.git
cd YDLidar-SDK
mkdir src
cmake ..
make
sudo make install
4-Test the installation
cd YDLidar-SDK/build
./tri_test
for X2L use 115200 [0] as baudrate
[Whether the Lidar is one-way communication[yes/no]:yes
when it works 
---------done!-----------
ydlidar driver with ros2 
1- Clone ydlidar_ros2_driver
from my repo email2
2- Build ydlidar_ros2_driver package:
cd ydlidar_ros2_ws
2_1- source
source /opt/ros/humble/setup.bash
source install/setup.bash
colcon build --symlink-install
------done!--------  

launch file with and without rviz
ros2 launch ydlidar_ros2_driver ydlidar_launch.py 

ros2 launch ydlidar_ros2_driver ydlidar_launch_view.py 

in laserScan select /scan as Topic and Best effort as Reliability policy

-----------done!----------------

SLAM with ydlidar X2 and ROS2


