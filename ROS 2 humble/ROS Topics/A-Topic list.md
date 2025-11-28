

|Category|Topic|Purpose|
|---|---|---|
|Motion Cmd|`/cmd_vel`|Move the robot|
|Motion Cmd|`/joint_trajectory`|Move a robotic arm|
|State|`/odom`|Robot position + velocity|
|State|`/joint_states`|Joint feedback|
|TF|`/tf`, `/tf_static`|Frames|
|Sensors|`/scan`|LiDAR|
|Sensors|`/imu`|IMU|
|Sensors|`/camera/image_raw`|RGB camera|
|Sensors|`/camera/depth/image_raw`|Depth|
|Sensors|`/gps/fix`|GPS|
|Nav|`/map`|Map|
|Nav|`/goal_pose`|Nav goal|
|Nav|`/initialpose`|AMCL init|
|Controller|`/controller_manager/*`|Control system|
|Diagnostics|`/diagnostics`|Health|


## Motion Command Topics:

  ### **➤ `/cmd_vel`**

- geometry_msgs/Twist
    
- Linear + angular velocity command
    
- For **diff drive**, **Ackermann**, **holonomic robots**, legged robots (sometimes).
    

 **➤ `/cmd_steer`** (Ackermann steering)

- For steering commands (if separated from throttle).
    

 **➤ `/cmd_drive`**

- Throttle + brake + steering (for car-like robots).
    
 **➤ `/joint_trajectory`**

- trajectory_msgs/JointTrajectory
    
- For manipulators (UR10, arms).

## State Feedback Topics:

**➤ `/odom`**

- nav_msgs/Odometry
- Robot’s estimated position + velocity.
- Generated from encoders, IMU, fusion, or wheels.
    

**➤ `/joint_states`**

- sensor_msgs/JointState
- Every joint’s:
    - position
    - velocity
    - effort
        

Published by `joint_state_broadcaster`.

**➤ `/tf` and `/tf_static`**

- geometry transforms
- backbone of robot’s frame tree
- used by:
    - navigation
    - RViz
    - controllers

## **Sensor Topics**

**➤ `/scan`**

- LaserScan
- LiDAR 2D output.
**➤ `/imu`**

- IMU readings: acceleration, gyro.
    
**➤ `/camera/image_raw`**

- camera feed.

**➤ `/camera/depth/image_raw`**

- depth image.

**➤ `/camera/points`**

- PointCloud2 (RGB-D or LiDAR).

**➤ `/gps/fix`**

- NavSatFix
- GPS coordinates.

## **Navigation / Mapping Topics**

**➤ `/map`**
- Occupancy grid map.
    
**➤ `/map_metadata`**

 **➤ `/goal_pose`**
 - For sending navigation goals.
    
**➤ `/global_costmap/**`

 **➤ `/local_costmap/**`**

**➤ `/initialpose`**

 - Set initial particle distribution for AMCL

## **Control (ros2_control) Topics**

**➤ `/controller_manager/list_controllers`**

 **➤ `/controller_manager/switch_controller`**

**➤ `/controller_manager/load_controller`**

**➤ `/controller_manager/unload_controller`**

**➤ `/diff_drive_controller/cmd_vel_unstamped`**


## **Diagnostics / Robot Health**

**➤ `/diagnostics`**
- Status of sensors, motors, power.
    
**➤ `/battery_state`**
- battery percentage, voltage, current.

## **Manipulation / Arm Topics**

**➤ `/joint_trajectory`**

- For MoveIt2.

**➤ `/tf`**, `/joint_states` (same as above)