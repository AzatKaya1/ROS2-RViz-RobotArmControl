# ROS2 l RViz l RobotArmControl
This guide aims to control the robot arm by integrating ROS2 with RViz.

**Note: This repository was created inspired by the official Franka_ROS2 GitHub page**

[Franka_ROS2 GitHub page](https://github.com/frankarobotics/franka_ros2)


1. Create a ROS 2 Workspace

```sh

mkdir -p ~/franka_ros2_ws/src
cd ~/franka_ros2_ws

```



2. Clone the Repositories


```sh

 git clone https://github.com/frankarobotics/franka_ros2.git src


```

3. Install the dependencies



```sh

vcs import src < src/dependency.repos --recursive --skip-existing


```

4. Detect and install project dependencies



```sh

rosdep install --from-paths src --ignore-src --rosdistro humble -y


```


5. Build


```sh



colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release

```
**If you encounter issues with the build process, follow the step below.**
```sh


sudo apt-get update
sudo apt-get install libgmock-dev

```




6. Adjust Enviroment


```sh

source install/setup.sh


```

## Test the Setup

Run the following code to control the robot arm using RViz

```sh

ros2 launch franka_fr3_moveit_config moveit.launch.py robot_ip:=dont-care use_fake_hardware:=true
```

**After opening RViz, you can start the "MotionPlanning" mode to practice with your robot arm.**




