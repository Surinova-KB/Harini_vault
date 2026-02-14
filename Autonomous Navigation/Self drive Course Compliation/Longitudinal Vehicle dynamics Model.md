
![[Pasted image 20260209145021.png]]

Rxr - Rolling resistance of rear wheel
Rxf - Rolling resistance of front wheel
F aero - Aero resistance 
Fxf - Front wheel force / torque
Fxr - Rear wheel force / torque 


#### State model :

   $$ m\ddot{x} = F_{xf} + F_{xr} - F_{aero} - R_{xf} - R_{xr} - mg sin\alpha $$
   simplified, $F_{xf}+F_{xr}=F_{x}$  and $R_{xf}+R_{xr}=Rx$ and  $\alpha$ is small so $sin\alpha = \alpha$
   $$  m\ddot{x} = F_{x}  - F_{aero} - R_{x} - mg\alpha $$
#### Simple Resistance Force Models:

 Total resistance Load :
   $$ F_{load} = F_{aero} + R_{x} + mg\alpha$$
   Aero dynamic forces depend on air density, frontal area , speed of vehicle
   $$ F_{aero} = 1/2 * C_{a} * \rho *A \dot{x}^2$$
   Rolling Resistance depend on tire normal force , tire pressure and vehicle speed
  $$ R_{x} = N(\hat{C}_{r,0} + \hat{C}_{r,1}|\dot{x}| + \hat{C}_{r,2}\dot{x}^2)  \approx C_{r,1}|\dot{x}|$$ 
#### Power Train Model:

  ![[Pasted image 20260209161457.png]]


  
  ### Rotational Coupling :
  
 $$\omega_{w} = GR\omega_{t} = GR\omega_{e} $$
$$\begin{aligned}
\omega_{w} = Wheel\ angular\ speed\\
  \omega_{t} = turbine\ angular\ speed\\
  \omega_{e} = Engine\ angular\ speed\\
  GR = combined gear ratios
  \end{aligned}  $$

  Longitudinal Velocity :

   $$ \dot{x} = r_{eff}\omega_{w} $$
    $$\begin{aligned}
     \dot{x} = Longitudinal\ velocity\\
     r_{eff} = Tire\ effective\ radius\\
     \end{aligned}$$
     
     

  Longitudinal Acceleration :

   $$ \ddot{x} = r_{eff}\ G\ R\ \dot{\omega}_{e} $$

   Power flow in powertrain:

   wheel :  $$ T_{wheels} = I_{w}\ \dot{\omega}_{w} + r_{eff} F_{x} $$
    $F_{x}$ = wheel force 
     $I_{w}$ = inertia of wheel

   Transmission : 
  $$  I_{t}\ \dot{\omega}_{t} = T_{t} - (GR) T_{wheel} $$
   Torque Converter :
  $$ \omega_{t}= \omega{e} $$
  $$ T_{t} = (I{t} + I_{w}GR^2)\dot{\omega}_{e} + GRr_{eff}F_{x} $$
   Engine : 
  $$ I_{e}\ \dot{\omega}_{e} = T_{engine} - T{t} $$

![[Pasted image 20260210133257.png]]
