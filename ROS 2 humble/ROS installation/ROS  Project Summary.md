
Phase 1 :

 Loading URDF into Gazebo sim - objective software in loop and physics
   1.Design to UARF with meshes (solid works), then visual files generated through blender using stl   from URDF.
   2.ROS package with URDF files and convert standard URDF to urdf.xacro - file format supported      by ROS. 
   3.Then generate joint limit files , transmission.xacro file to define joints and actuators .
   4.Gazebo.xacro file to define simulation and ros bridge specifications for the robot .
   5.Launch.py file to link and load URDF to Gazebo world.

Phase 2 : 

  Implementing Robot control using existing controller - objective  study potential   libraries,      controller ,it's working and how to implemented.
   1.Control the robot using Differential drive controller provided by ROS ,to actuate only wheels, publishing velocity and controlling rover through keyboard inputs.
   2.Control rover using Ackermann steering control provided by ROS, to actuate steering joint and wheels joint at the same time.
   3.Developed a customized controller to control only wheels (reference diff_drive),


Phase 3 :

   Implementing control in Rpi 4 with ROS humble as middle ware - objective To verify multi thread handling and ROS2 middle ware functionalities
   1.Run a publisher and subscriber in Rpi to test ROS functionals.
   2.Publish velocity and run a motor with odrive (commands sent via UART from Rpi).
   3.Send velocity over SPi via RPi and implement a SPI to CAN via MCP module (yet to complete)

