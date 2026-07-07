# Mobile Robot – Mecanum Drive with Multi-Sensor Perception (ROS 2 Jazzy)

A mecanum-drive mobile robot simulated in Gazebo, built on ROS 2 Jazzy, designed to perceive and interact with a sandbox environment using fused sensor data and real-time computer vision.

## Overview
This project combines LIDAR and RGBD camera data for spatial awareness, alongside an OpenCV-based vision pipeline that detects and tracks a red ball, driving closed-loop following behavior in simulation.

## Key Features
- **Sensor Fusion**: Integrates `PointCloud2` data from an RGBD camera with 2D LIDAR scans to build a combined spatial understanding of the environment.
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
