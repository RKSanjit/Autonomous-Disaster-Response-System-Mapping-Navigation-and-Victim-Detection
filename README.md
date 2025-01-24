# Autonomous System for Disaster Response: Navigating and Mapping Hazardous Environments

## Objective  

This project focuses on designing and implementing a complete autonomous system to conduct reconnaissance in a simulated disaster environment.

1. **Environment Mapping:** Automatically generate a detailed occupancy grid map of the unknown environment to aid in visualizing the area and planning safe navigation paths.

2. **Victim Location:** Identify simulated victims, represented by AprilTags, within the environment and provide their ID numbers and precise locations on the map.

---

## Installation  

- Ubuntu  
- Python  
- ROS  

---

## Required Packages  

- GMapping  
- Cartographer  
- explore_lite  
- apriltag_ros  

---

## Process  

1. **Robot Deployment:** The robot is placed in an unknown environment to initiate the reconnaissance mission.  

2. **SLAM with GMapping:** The **gmapping** package is used to perform real-time SLAM (Simultaneous Localization and Mapping), creating a map of the environment while tracking the robot's position.  

3. **Autonomous Exploration:** The **explore_lite** package is implemented for autonomous navigation. This enables the robot to systematically explore the unknown environment using a greedy frontier-based algorithm.  

4. **Map Generation:** The **explore_lite** package is used during exploration to continuously update and complete the occupancy grid map of the environment.  

5. **AprilTags Detection:** The **apriltag_ros** package detects AprilTags within the environment, interprets them as simulated victims, and logs their global poses.  

6. **Mission Completion:** The operation concludes once the robot has fully explored the environment and all AprilTags are detected and logged.  

---

## Extension: Enhancing SLAM and AprilTags Detection with Cartographer  

To improve SLAM accuracy and reliability, the Cartographer package was integrated into the system. Cartographer uses multi-sensor fusion, incorporating LIDAR, IMU, and camera data, to enhance mapping and localization. This addition improved AprilTags detection and tracking, enabling robust loop closure, which is essential for precise robot positioning and orientation in complex environments.  

---

## Conclusion  

### Summary  

This project successfully developed an autonomous system for disaster response, focusing on mapping and victim detection. Initial trials with **gmapping** and **explore_lite** enabled the robot to map the environment accurately but detected only five of seven AprilTags due to limitations in LIDAR settings and field of view. To address these challenges, the Cartographer package was integrated. Its multi-sensor fusion capabilities significantly enhanced SLAM accuracy and reliability, enabling a more comprehensive environmental map and ensuring all AprilTags were accurately detected. This achievement marks substantial progress in the development of autonomous systems for disaster response.  
