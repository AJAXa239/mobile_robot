# ROS_bot_car
Designed a mecanum-drive mobile robot in Gazebo (ROS 2 Jazzy) that fuses LIDAR and RGBD camera point cloud data to perceive a sandbox environment, with an OpenCV/CvBridge vision node that detects a red ball and drives closed-loop tracking and following behavior. Integrated PointCloud2 data from the RGBD camera sensor alongside LIDAR scans for spatial awareness, and implemented the detection-to-motion pipeline that converts image-space ball position into real-time drive commands.
# mobile_robot
