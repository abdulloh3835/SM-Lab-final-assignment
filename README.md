# SM-Lab-final-assignment
# Final Project - ROS 2 TurtleBot3 Controller

![TurtleBot3](link-to-turtlebot3-image.jpg) <!-- Include an image if you have one -->

## Overview

Welcome to the Final Project ROS 2 TurtleBot3 Controller! This project aims to provide a versatile and extensible ROS 2 controller for the TurtleBot3 robot. The controller introduces the "move_turtle" action, empowering users to seamlessly interact with the robot, commanding it to execute precise and dynamic movements.

## Key Features

- **Customizable Motion Goals:** Users can send goals to the TurtleBot3, defining both linear and angular velocities, as well as a duration for the robot to execute the specified movements.

- **Simulation Integration:** The project seamlessly integrates with Gazebo for simulation purposes, allowing users to test and visualize the robot's behavior in a controlled environment.

- **Action Monitoring:** Easily monitor the real-time status of the ongoing actions, facilitating comprehensive feedback during the execution of goals.

## Project Structure

1. **ROS 2 Workspace (`ros2_ws`):**
    - Path: `/home/abdullokh3835/ros2_ws`

2. **Final Project Package (`final_project`):**
    - Source File: `/home/abdullokh3835/ros2_ws/src/final_project/src/final_project_turtlebot.cpp`
    - CMakeLists.txt: `/home/abdullokh3835/ros2_ws/src/final_project/CMakeLists.txt`
    - Package Description: `/home/abdullokh3835/ros2_ws/src/final_project/package.xml`

3. **My Robot Bringup Package (`my_robot_bringup`):**
    - Launch File: `/home/abdullokh3835/ros2_ws/src/my_robot_bringup/launch/final_project_turtlebot.launch.xml`
    - CMakeLists.txt: `/home/abdullokh3835/ros2_ws/src/my_robot_bringup/CMakeLists.txt`
    - Package Description: `/home/abdullokh3835/ros2_ws/src/my_robot_bringup/package.xml`

4. **My Robot Interfaces Package (`my_robot_interfaces`):**
    - Action File: `/home/abdullokh3835/ros2_ws/src/my_robot_interfaces/action/MoveTurtle.action`

## Prerequisites

Before using this controller, ensure that you have the following prerequisites installed:

- [ROS 2 Humble](https://docs.ros.org/en/humble/Installation.html)
- Gazebo (for simulation)
- TurtleBot3 model (e.g., "waffle")

## Installation

1. Set the environment variable for the TurtleBot3 model:

    ```bash
    export TURTLEBOT3_MODEL=waffle
    ```

2. Launch the Gazebo simulation with an empty world:

    ```bash
    ros2 launch turtlebot3_gazebo empty_world.launch.py
    ```

3. Launch the ROS 2 component container:

    ```bash
    ros2 launch final_project turtlebot_controller.launch.py
    ```

## Usage

### Sending a Goal

To instruct the TurtleBot3 to perform specific movements, send a goal using the following ROS 2 command:

```bash
ros2 action send_goal /turtle_controller_1 final_project/MoveTurtle "{linear_vel_x: 1.0, angular_vel_z: 0.5, duration_sec: 10}"
