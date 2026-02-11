## Requirements of Autonomy:

Perception , prediction and planning the drive. 

Estimating environmental elements that influence driving. 

Breakdown task of driving into elemental decision and actions.

Assess Effect of driving condition on driving task.

 ### Terminology of self driving systems :

   Driving Task :

   1. Perception  -  perceiving environment 
   2. Motion planning  -  obstacles , path to take and angle to turn 
   3. Vehicle operation (vehicle control)  -  control steering , break and acceleration in close loop control.

  ### Operational Design domain(ODD):

   1. Characteristic of the system for which it's been designed, like environment , time of the day ,roadway etc.,
   2. Operating condition for which the self driving vehicle is designed 


  ### Classification of driving system automation:

   1.  Driver attention requirements
   2.  Driver action requirements
   3.  What exactly makes up a driving task?
  
   Driving Task (Automation task break down):

   1. Lateral control - steering 
   2. Longitudinal control - position and velocity of the car 
   3. OEDR - Object and event detection and Response
   4. Planning - long and short term plans needed to travel to a destination.

  Autonomous Capability:

   1. Level zero - No Automation
   2. Level one - Driving Assistance (either lateral or longitudinal)
   3. Level two - Partial Driving Automation (autonomous in simple scenario)
   4. Level three - OEDR to a certain degree with lateral n longitudinal
   5. Level four - High driving Automation -System handles emergency on it's own still needs driver to take over
   6. Level five - Full driving automation - Can operate under any condition

  
## Requirement for Perception:

   1. OEDR 
   2. Dynamic trajectory prediction of moving bodies in the environment 

  ### Perception goals :

   Identify static elements - lanes , road markings, off road elements, traffic signal
   Identify dynamic objects - adjacent vehicles 

 Perception subsystem must be designed in a way to accumulate uncertainty and corrupted data in every task.

  Occlusion and precipitation can hinder the process of perception greatly.