
Car model based on bicycle model.

Assumptions: 

  Longitudinal velocity is constant 
  Left and right axle are lumped as single wheel
  Suspension movement , road inclination and aerodynamic influences are neglected (but IRL these has major effect in dynamics)


### Lateral Dynamics :

  $$ a_{y} = \ddot{y}+ \omega^2 R = V\dot{\beta} + V\dot{\psi} $$
 $$ \begin{aligned}
 a_{y} = total acceleration\\ 
 \ddot{y} = Lateral acceleration\\
 \omega^2 R = Centripetal\ aceeleration\\ due\ to\ circular\ motion\\
 \dot{\beta} = Lateral\ slip angle\ rate\ of\ change \\ 
 \dot{\psi} = Heading rate of change
 \end{aligned}$$

Two forces affecting dynamics is the lateral force in the tire and the vehicle velocity and the mass
  Lateral Force Balance : Newton's 2nd law
$$ m V ( \dot{\beta} + \dot{\psi}) = F_{yf} + F_{yr} $$ 
for angular acceleration:
  Yaw movement :(Rotational Dynamics)
  $$ I_{z}\ddot{\psi} = L_{f}F_{yf} - L_{r}F_{yr}  $$

  $$ I_{z} - inertia of vehicle \
 L_{r}\ and\ L_{f} - distance of CG from front and rear wheel $$

### Tire Slip Angles:


  For smaller tire slip angle, the lateral tire force are approx as a linear function of tire slip angle

  Front tire slip  $\alpha_{f}$ 
  rear tire slip  $\alpha_{r}$

  ![[Pasted image 20260211155745.png]]

![[Pasted image 20260211155815.png]]


### Front and rear Tire forces :



  Lateral force linearly depend on the slip angle of the tire and the constant coeff is called cornering stiffness.
  
   ![[Pasted image 20260211155940.png]]

   $$ \begin{aligned}
   F_{yf} = C_{f}\alpha_{f} = C_{f} ( \delta - \beta - (l_{f}\dot{\psi}/V))\\ 
    F_{yr} = C_{r}\alpha_{r} = C_{r} (  - \beta + (l_{f}\dot{\psi}/V)) 
   \end{aligned}$$

   after substituting lateral forces, from above dynamics equations 
   $$
\begin{aligned}
\dot{\beta} &= -\frac{(C_r + C_f)}{mV}\,\beta 
+ \left( \frac{C_r l_r - C_f l_f}{mV^2} - 1 \right)\dot{\psi} 
+ \frac{C_f}{mV}\,\delta \\[8pt]
\ddot{\psi} &= \frac{C_r l_r - C_f l_f}{I_z}\,\beta 
- \frac{C_r l_r^2 + C_f l_f^2}{I_z V}\,\dot{\psi} 
+ \frac{C_f l_f}{I_z}\,\delta
\end{aligned}
$$
   gives the dynamics equation in lateral direction 


### State space representations:

  State vector:
  $$ X_{lat} = [y\ \beta\ \psi\ \dot{\psi}]^T $$
   $$ \begin{aligned}\\
   y = lateral position\\
 \beta = side slip angle\\
 \psi = yaw angle\\
  \dot{\psi} = yaw rate 
  \end{aligned}$$
### Standard State space representation :
  ==$$
\dot{X}_{lat} = A_{lat} X_{lat} + B_{lat}\,\delta
$$==


$$
A_{lat} =
\begin{bmatrix}
0 & V & V & 0 \\[6pt]
0 & -\dfrac{C_r + C_f}{mV} & 0 & \dfrac{C_r l_r - C_f l_f}{mV^2} - 1 \\[10pt]
0 & 0 & 0 & 1 \\[6pt]
0 & \dfrac{C_r l_r - C_f l_f}{I_z} & 0 &
-\dfrac{C_r l_r^2 + C_f l_f^2}{I_z V}
\end{bmatrix}
$$

$$
B_{lat} =
\begin{bmatrix}
0 \\[6pt]
\dfrac{C_f}{mV} \\[10pt]
0 \\[6pt]
\dfrac{C_f l_f}{I_z}
\end{bmatrix}
$$
  Steering angle is the input to this system of equation and it's time variant with constant velocity.