![ROS2](https://img.shields.io/badge/ROS2-Jazzy-blue)
![Issues](https://img.shields.io/github/issues/AJAXa239/mobile_robot)
![Last Commit](https://img.shields.io/github/last-commit/AJAXa239/mobile_robot)
![Stars](https://img.shields.io/github/stars/AJAXa239/mobile_robot)
# Mobile Robot Mecanum Drive with Multi-Sensor Perception (ROS 2 Jazzy)

A mecanum-drive mobile robot simulated in Gazebo, built on ROS 2 Jazzy, designed to perceive and interact with a sandbox environment using fused sensor data and real-time computer vision.

## Overview
This project combines LIDAR and RGBD camera data for spatial awareness, alongside an OpenCV-based vision pipeline that detects and tracks a red ball, driving closed-loop following behavior in simulation.

## Key Features
- **Sensor Fusion**: Integrates `PointCloud2` data from an RGBD camera with LIDAR scans to build a combined spatial understanding of the environment.
- **Mecanum Drive Kinematics**: Supports omnidirectional movement (forward/backward, strafing, rotation) using a 4-wheel mecanum drive configuration.
- **Vision-Based Object Tracking**: An OpenCV + CvBridge node detects a red ball in the camera feed and converts its image-space position into velocity commands.
- **Closed-Loop Following**: The robot continuously adjusts its heading and speed to track and follow the detected object in real time.
- **Simulation Environment**: Fully simulated in Gazebo Harmonic, including a custom world, robot URDF/xacro description, and sensor plugins (LIDAR, RGBD camera, IMU).

## Tech Stack
- ROS 2 Jazzy
- Gazebo Harmonic
- OpenCV / cv_bridge
- Python (rclpy)
- URDF / Xacro

## Packages
- `bme_gazebo_sensors` — robot description, world files, launch files, sensor configuration
- `bme_gazebo_sensors_py` — Python nodes including the ball detection and tracking pipeline (`chase_the_ball.py`)

## Motivation
Built as part of an ongoing robotics portfolio, this project explores multi-sensor perception and closed-loop control pipelines relevant to autonomous mobile robotics applications.

## Command
- colcon build --packages-skip moveit_ros_tests --allow-overriding mecanum_drive_controller moveit_common moveit_core moveit_ros_planning --cmake-args -Wno-dev
- ros2 launch bme_gazebo_sensors spawn_robot.launch.py
- ros2 run bme_gazebo_sensors_py chase_the_ball
- ros2 run bme_gazebo_sensors_py gps_waypoint_follower

## Images
![image](https://github.com/AJAXa239/mobile_robot/blob/03045d69d4a119fb72dd5d9cacab76f65287dba8/assets/Screenshot%20from%202026-07-07%2013-06-58.png)
