
(1) URDF + ros2_control
         ↓
         
(2) Hardware Interface
             ↓
        
(3) Controller Manager
         ↓
         
(4) Controllers (Ackermann, DiffDrive, Joint Traj)
         ↓
         
(5) Command interfaces → back to Hardware


### URDF **declares**:

- joints
    
- limits
    
- ros2_control hardware plugin
    
- command/state interfaces

  It describes the robot .

### Hardware Interface:

   This is the plugin that:

- exports **state interfaces** (encoder positions, velocities)
    
- exports **command interfaces** (to motor drivers)
    
- reads sensors
    
- writes to hardware or Gazebo
    

  It is the bridge between **ROS2** and **motors/encoders/physics**.


### Controller Manager:

  This is the **scheduler**.

   Every control cycle:

 1. Calls **hardware.read()**
    
 2. Calls **controller.update()**
    
 3. Calls **hardware.write()**
    

   It loads controllers, configures them, and runs them.


### Controllers:

   Code block that inherits from controller interface and defines what control cation to be taken.

- read joint states (from hardware)
    
- compute control (PID, kinematics, Ackermann, diff drive)
    
- write velocities/positions into command interfaces
    
- accept command topics (e.g., /cmd_vel)
    

  Controllers NEVER talk to hardware directly.

  They _only_ write into **command_interfaces[]**.

### Controller Interface :

   A base class from which controllers are inherited

    controller_interface::ControllerInterface


  It defines the **rules** for what a controller must implement

  **Life-cycle Management**
    This keeps controllers well-behaved and modular.
  **Handle Joint Interfaces**
    How many state interfaces and command interface to work with 
   **Define the Update Loop**
     This is where your algorithm lives and control loop implements at the specified time interval
   **Provide ROS interfaces**
     publishing, subscribing, requesting service etc., to other nodes and topics
   **Connect to Controller Manager**
