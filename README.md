# ros2-potential-field-navigation
ROS 2 implementation of potential field-based path planning for autonomous navigation. Features dynamic obstacle avoidance using LaserScan data in Gazebo.

## Team
**Project developed at Hochschule Bonn-Rhein-Sieg (H-BRS) - Autonomous Systems**

* **Adnan Kanchwala**
* **Ibrahim**
* **Evenzer**

*Collaborative implementation of the Potential Field algorithm and parameter tuning.*

# Potential Field Path Planning with ROS 2

This project implements a **Potential Field-based** local path planner for the 'Robile' autonomous platform. The system calculates real-time velocity commands to navigate the robot to a specific goal pose while avoiding dynamic obstacles detected via LiDAR.

## Key Features
* **Dynamic Obstacle Avoidance:** Uses `LaserScan` data to calculate repulsive forces from nearby obstacles.
* **Goal Attraction:** Implements attractive potential logic to guide the robot to coordinates `[4.0, 10.0, -1.0]`.
* **Real-time Control:** Publishes velocity commands to `/cmd_vel` based on the summed force vectors.
* **Frame Transformation:** Handles `tf2` transformations between the Odom and Base_Link frames.

## Technology Stack
* **Framework:** ROS 2 (Humble/Foxy)
* **Language:** Python / C++
* **Simulation:** Gazebo & Rviz
* **Math:** Vector calculations for Attractive ($F_{att}$) and Repulsive ($F_{rep}$) fields.

## How it Works
The planner subscribes to the `/scan` topic. For every laser reading within a threshold distance ($\rho_0$), a repulsive vector is generated. These are summed with the attractive vector pointing toward the goal. The resulting vector is converted into linear and angular velocity commands.

## Credits & Disclaimer
This project was developed as part of the **Autonomous Systems** coursework. 
* **Simulation Framework:** The 'Robile' robot simulation and Gazebo environment assets are provided by the course instructors.
* **Path Planning Logic:** The potential field algorithm implementation (`planner.py` / `node`) is my own contribution for educational purposes.

*Note: This code is intended for portfolio demonstration and learning reference.*
