
###  Sensors and Computing Hardware:

  
  Sensor is to perceive the environment in real time for reactive planning and prediction planning.

   ### Perception sensor - Camera :

   Cameras are a passive, light-collecting sensor that are great at capturing rich, detailed information about a scene

   We select cameras in terms of their *resolution*. The resolution is the number of pixels that create the image. So it's a way of specifying the quality of the image.
   
   We can also select cameras on the basis of *field of view*. The field of view is defined by the horizontal and vertical angular extent that is visible to the camera, and can be varied through lens selection and zoom.

   The *dynamic range* of the camera is the difference between the darkest and the lightest tones in an image. High dynamic range is critical for self-driving vehicles due to the highly variable lighting conditions encountered while driving especially at night.

   The combination of two cameras with overlapping fields of view and aligned image planes is called the stereo camera. **Stereo cameras allow depth estimation from synchronized image pairs.**

   Perception sensor - LIDAR :

   LIDAR sensing involves shooting light beams into the environment and measuring the reflected return.
   It is an active sensor with it's own light sources, LIDAR are not effected by the environments lighting.

   The first is the number of sources it contains with 8, 16, 32, and 64 being common sizes. And the second is the *points per second* it can collect.
   The faster the point collection, the more detailed the 3D point cloud can be.

   The higher the *rotation rate*, the faster the 3D point clouds are updated.
   
   Perception sensor - RADAR :

   RADAR sensors have been around longer than LIDAR and robustly detect large objects in the environment.

   They are particularly useful in adverse weather as they are mostly unaffected by precipitation.

   RADAR are selected based on detection range, field of view, and the position and speed measurement accuracy.

   RADAR are also typically available as either having a wide angular field of view but short range. Or having a narrow filed of view but a longer range.


   Perception sensor - Ultrasonics :

   Sonar are sensors that are short range in inexpensive ranging devices.

   They are unaffected by light, perception and climatic conditions.

   Key metrices to select the sonar are ,the maximum range they can measure, the detection field of view, and their cost.


  Perception sensor - GNSS/IMU:

  Direct measure of ego vehicle states

- position,velocity(GNSS)
    - Varying accuracies : RTK,PPP,DGPS
- angular rotation rate(IMU)
- acceleration(IMU)
- heading(IMU,GPS)

  