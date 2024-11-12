# ESIM_Event_Generator
This is a complete guide on how to install ROS and the ESIM simulator to generate event data.

To install the ESIM, you should have the ROS, if you have it on your system then follow this link: https://github.com/uzh-rpg/rpg_esim/wiki/Installation
otherwise, please follow these steps:

-- To install the ROS Kinetic, you should use the Ubuntu 16.04 version or a lower version, so if you don't have it try to install it.
-- After installing the ubuntu, install python3 and pip3:
-- Sub sudo apt-get update
-- Sub sudo apt-get install python3-pip

-- Now, let's install the ROS (https://wiki.ros.org/kinetic/Installation/Ubuntu)
-- Sub sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
-- Sub sudo apt install curl # if you haven't already installed curl
-- Sub curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
-- Sub sudo apt-get update
-- Sub sudo apt-get install ros-kinetic-desktop-full
-- Sub apt-cache search ros-kinetic
-- Sub echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
-- Sub source ~/.bashrc
-- Sub sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
-- Sub sudo apt install python-rosdep
-- Sub sudo rosdep init
-- Sub rosdep update

-- Until now, ROS has been installed, now let's install the ESIM, if you don't have the catkin use the below commands first (not all of them, depends on the errors that you may get):
-- Sub sudo apt-get install ros-kinetic-catkin
-- Sub  sudo apt-get install cmake python-catkin-pkg python-empy python-nose python-setuptools libgtest-dev build-essential
-- Sub  mkdir build && cd build && cmake ../ && make && sudo make install
-- Sub  sudo apt-get install cmake python-catkin-pkg python-empy python-nose libgtest-dev
-- Sub  sudo pip install -U catkin_pkg
-- ESIM:
-- new workspace:
-- Sub mkdir -p ~/sim_ws/src && cd ~/sim_ws
-- Sub catkin init
-- Sub catkin config --extend /opt/ros/kinetic --cmake-args -DCMAKE_BUILD_TYPE=Release
-- Sub sudo apt-get install python-vcstool
-- clone the esim repository: 
-- Sub cd src/
-- Sub git clone git@github.com:uzh-rpg/rpg_esim.git
-- Sub vcs-import < rpg_esim/dependencies.yaml
-- Sub if you have any problems in related to cloning, try to generate a new ssh key (https://www.youtube.com/watch?v=m5hg07zLn4U&ab_channel=KDTechs)
-- sudo apt-get install ros-kinetic-pcl-ros
-- sudo apt-get install libproj-dev
-- sudo apt-get install libglfw3 libglfw3-dev
-- sudo apt-get install ros-kinetic-hector-trajectory-server
-- cd ze_oss
-- touch imp_3rdparty_cuda_toolkit/CATKIN_IGNORE \
      imp_app_pangolin_example/CATKIN_IGNORE \
      imp_benchmark_aligned_allocator/CATKIN_IGNORE \
      imp_bridge_pangolin/CATKIN_IGNORE \
      imp_cu_core/CATKIN_IGNORE \
      imp_cu_correspondence/CATKIN_IGNORE \
      imp_cu_imgproc/CATKIN_IGNORE \
      imp_ros_rof_denoising/CATKIN_IGNORE \
      imp_tools_cmd/CATKIN_IGNORE \
      ze_data_provider/CATKIN_IGNORE \
      ze_geometry/CATKIN_IGNORE \
      ze_imu/CATKIN_IGNORE \
      ze_trajectory_analysis/CATKIN_IGNORE
-- catkin build esim_ros
-- echo "source ~/sim_ws/devel/setup.bash" >> ~/setupeventsim.sh
-- chmod +x ~/setupeventsim.sh
-- Add to bash:
-- sub nano .bashrc
-- Sub add this: alias ssim='source ~/setupeventsim.sh' 
-- Sub then Ctrl+x and yes to save and exit
-- Finished :)

From now on, typing ssim in a terminal will initialize the simulator workspace (you need to run bash first if you want to try this right after editing the .bashrc file.
