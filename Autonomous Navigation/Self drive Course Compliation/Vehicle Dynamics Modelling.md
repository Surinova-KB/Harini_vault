

### Kinematics Vs Dynamics:

   Kinematics - analyzing velocity and acceleration of the vehicle 

   Dynamics - analyzing forces involved 

   At low speed only kine model is sufficient but dynamics model captures vehicle behavior more precisely.

  
### Coordinate Frames :

  Coordinate frames used are Right handed by convention.
  
  Standard coordinate frames used :
   *Inertial Frames* - fixed world frame(earth) often represented as ENU(east north up) or Earth center earth Frame (ECEF) used in GNSS.

   ==Typical coordinates pipeline==: ECEF → LLH → ENU → Robot frame


   *Body frame* - Attached to vehicle , usually at the center of gravity.

   *Sensor Frame* - Frame attached to each sensor in the system


### Coordinate Transformation:

   Any vector quantity relative to the vehicle needs to be transformed ad rotated in order to obtain necessary value in the required point or frame .

 Rotation about X :

  $$ Rx =  
  \begin{bmatrix}
  1&0&0\\
  0 & cosθ & -sinθ \\
  0&-cosθ&sinθ
  \end{bmatrix}
  $$
   Rotation about Y:

  $$ Ry =  
  \begin{bmatrix}
  cosθ&0&sinθ\\
  0 & 1 & 0 \\
  -sinθ&0&cosθ
  \end{bmatrix}
  $$
   Rotation about Z:

  $$ Rz =  
  \begin{bmatrix}
  cosθ&-sinθ&0\\
  sinθ & cosθ & 0 \\
  0&0&1
  \end{bmatrix}
$$

Translation : 

   P = [x' , y' , z']   position vector of a point in a frame which is translated 

#### Homogeneous transformation matrix:

 $$ T =  
  \begin{bmatrix}
  R&P\\
  000 & 1 \\ 
  \end{bmatrix}\ \  4X4 matrix
$$


Simple 2D model 

   A body moving in 2d plane with a velocity V then the components of velocity are 

   ẋ = v cosθ   ẏ = v sin θ 

   Input   --- >  Model  --->  States (o/p)

  Model calculates  $\dot{x}$ , $\dot{y}$ and $\dot{θ} = w$
  
  Output represents the three states of the robot.
  
  
## Kinematic Modelling :


## Dynamic Modelling:


  At high speed , vehicle tend to slip in the track and to avoid this slippery force acting on the vehicle need to be modeled.

   Steps to build a typical dynamic model:

   $$ \sum F= ma $$
  $$ \sum 𝑇=𝐽𝛼 $$

   Coordinate frames ---> Lumped dynamic elements ---> Free body diagram ---> Dynamic equation

### Translational Dynamics:

  Dynamics in y direction is constant N = Mg while for the x direction,
   $$ \sum M\ddot{x} = F1+F2+F3 ... $$

### Rotational Dynamics:

   Jθ + b $\dot{θ}$+k $\ddot{θ}$ = T drive - T load 


 