
Odometry is a feed back estimate of robot's position , yaw orientation and position relative to world frame. It mainly estimates robot's velocity using wheel encoder.

In basic project's where model doesn't include an encoder it estimates a fake odom from cmd_vel value that's fed as input.

In ROS , odometry is published as a topic /odom  ----  /nav_msg/odometry

==odometry is basically a node, topic and msg all in one.==
==The odometry node computes velocity, position and orientation from cmd_vel or wheel tick and publishes the now formed odometry msg into odometry topic.==

This is used by:

- Navigation stack (e.g., navigation2)
    
- Localization (e.g., EKF, AMCL)
    
- SLAM
    
- Controllers (like `diff_drive_controller` if wheel feedback exists)

Working :

 given velocity: V and ω

  x(t+Δt) = x(t) + v * cos(θ) * Δt
  y(t+Δt) = y(t) + v * sin(θ) * Δt
  θ(t+Δt) = θ(t) + ω * Δt

   that's how position and orientation is calculated.

  For the input Velocities come from : wheel encoders (REAL odometry),
                              From IMU (dead-reckoning odometry),
                              From simulation (Gazebo, Isaac Sim),
                              ==From nothing (no encoders, no IMU)“fake odometry"= integrate your own cmd_vel  (this isn't real feedback, just expected arbitrary values)==


