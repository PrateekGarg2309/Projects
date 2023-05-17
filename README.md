# Project1 : Controlling the position of X-stage of a WireBonding system

Description -

![MSD1 ](https://github.com/PrateekGarg2309/Projects/assets/133784841/566697f4-ddf2-4dd1-8620-9158e6449e15)

A  model of a Wire-Bonder motion system is considered for this project, which is developed by ASMPT, a company specializing 
in the development of high-end mechatronic machines. Wire bonding is the method of making interconnections between an integrated circuit (IC) 
or other semiconductor device and its packaging during semiconductor device fabrication. To accommodate ever smaller more densely packaged
components, the requirements for desired precision are ever increasing alongside the desired high throughput of the system. This necessitates 
the need to have a finely tuned control system in place to meet these speed and precision 
requirements. Figure presents a model of the motion system in consideration. The goal is to control the position x2
of the x-stage using the input force Fx.

Steps Involved -

1. Deriving and plot the transfer functions from Fx to x2 and Fx to x3. Comment on the observed 
differences
2. Plotting the frequency response of the system via a Bode Plot using the data below
![data](https://github.com/PrateekGarg2309/Projects/assets/133784841/189fe9cb-9416-415d-975c-396a9514f6f0)
3. Performing a modal analysis of the system by deriving the system matrices and the eigenvalues, 
and explain the behaviour of the system in the low and high-frequency regimes, including the 
behaviour at the observed resonance/antiresonance peaks
4. Identifying the system using the approach presented during the lecture on system identification 
in the frequency domain. A chirp signal was used.
5. The system is subjected to a transport delay due to the sampling (𝑡𝑠=0.125 ms). The delay is introduced to the system in 
before as modal analysis and the modified frequency response of the system is presented.
6. Designing a PID-type controller for the system that assures the phase margin 𝑃𝑀≥30∘
, gain margin 𝐺𝑀≥6dB, modulus margin MM≤6dB, and zero steady-state error for a step response, 
with the highest possible bandwidth.
7. The bode plot of the designed controller, complementary sensitivity, and sensitivity 
functions of the designed control system along with the stability margins using relevant plots are presented.
8. Implementing the designed controller for the plant MSD2022Plant in Simulink with a reference 
profile provided in referenceProfile_4mm_20G for the x-position
9. Plotting the step response of the system. Present the rise time, settling time, and overshoot
10. Implement a feedforward controller based on the reference profile in the designed control 
system in Simulink
11. Analyzing the difference in the performance (reference tracking and disturbance rejection) 
of the feedback-controlled system, with and without the feedforward control, using plots

Model:
![1](https://github.com/PrateekGarg2309/Projects/assets/133784841/85bbc0b3-9bba-4dcf-bb71-1e11009e1a5f)
![2](https://github.com/PrateekGarg2309/Projects/assets/133784841/49b5ada7-a2a9-4251-97bc-26e1f2258db5)


# Project2 : Investigating the resonances and the mode shapes of a Hand-Arm Vibration system

Description - 

![image1](https://github.com/PrateekGarg2309/Projects/assets/133784841/49937a8a-0225-410b-9dca-5ba7f91bed79)
![image2](https://github.com/PrateekGarg2309/Projects/assets/133784841/9f04fa92-4c85-4170-9f4e-03c1367d21fa)

Aspects of control relating to the accuracy of the CD actuator are taken into account here. The controller designed
allows us to achieve the required position accuracy when disturbances are present. The dynamic model of the mechanical structure is, 
however, extremely simple. In reality the internal dynamics of the actuator play an important role. To make a simple model for 
the radial direction we can look at the top-view of the actuator. The hinges of the suspension support the total mass at a frequency
of about 40 Hz. The radial force is applied at the radial coil. The radial displacement of the lens is measured.
The design has a certain resemblance to a set of book-shelves. The lens, the radial coil and the focus coil can
be seen as rigid in radial direction and are connected by two upright stands. For the radial dynamics a first approximation with 
3 masses and connecting springs can be used. The mass, stiffness and damping of the different connections and the sensor (o) and actuator (F) are
indicated in the figure.

Steps Involved -
1. Developing a model for the CD-head including these internal dynamics. Set the PID controller to a 800 Hz BW using the values obtained
using the PID rules of thumb. The actuator BW and controller delay are not considered in this model.
2. Separating the lens-assembly into different masses had considerable effects on the control of the actuator. Checking that the
above model leads to the open loop transfer in figure below
![image3](https://github.com/PrateekGarg2309/Projects/assets/133784841/d00ed107-0851-4a5e-ab84-8af2073d8c9f)
3. Checking the open loop transfer function stability using Nyquist
4. Varying the lens-radial coil stiffness from 1000 kN/m, to 150 kN/m and 100 kN/m and note the effect on
the dynamic behavior in Bode-plot and Nyquist.
5.  Finding the most suitable value for the lens-body stiffness by testing different values on that range and observing the Bode and Nyquist
plots and obtained the best mechanical system
6. Had an improved mechanical design that unfortunately in combination with the chosen PID-controller results
in an unstable system. Therefore, added a low-pass 1st -order filter to the controller with an optimal BW-frequency, and observe the effect
in the Nyquist-diagram and Bode-plot

Simulink Model - 
![Predictive Modelling](https://github.com/PrateekGarg2309/Projects/assets/133784841/230f17f2-26aa-4427-8d99-b9eeb34f76da)


# Project3 : Investigating the resonances and the mode shapes of a Hand-Arm Vibration system

Description -

![ED](https://github.com/PrateekGarg2309/Projects/assets/133784841/9fa54c73-60b5-43b8-9cb1-c9c5bb9a7723)

If modelled with all its complexities, the hand-arm vibratory system is a three-dimensional problem
consisting of many degrees of freedom. The muscles are continuum elements that show viscoelastic
behavior upon loading, and bones are stiff parts that undergo elastic deformations when subjected
to external forces. This was done by using a simple model comprising discrete mechanical
elements to explain the dynamics of this system. goal is to model the motion only in the x − y plane. 
For this we use three masses (m1, m2, and m3), five translational springs (k1 − k5), one rotational spring (kt3),
five translational dampers (c1 − c5), and one rotational damper (ct3). Masses m1, m2, and m3 represent the
palm, lower arm, and upper arm, respectively. J3g is the mass moment of inertia for m3 with
respect to its center of mass. The upper arm (m3) is attached to the lower arm (m2) with the
elbow joint and to the body (environment) with the shoulder joint. Lg shows the center of mass of
the upper arm with respect to the elbow joint whose total length is L. On the other hand, ˜θ is the
orientation of the upper arm while working with the hand-held vibratory tool. For the worker’s
comfort, and ease of usage of the vibrating tool, it is desired that this angle remains constant while
using the tool.

Steps Involved -
1. Finding an expression for the kinetic energy T, potential energy V and dissipation function D of the
system
2. Using Lagrange equations to obtain the governing equations
3. Linearizing the dynamic equations around the operational configuration (˜θ) and find the linearized mass, damping, and stiffness matrices
4. Calculateing the eigenfrequencies and eigenmodes of the system without damping
5. Calculating the eigenfrequencies and eigenmodes of the system with damping and also finding the corresponding damping ratio for each eigenfrequency
6. Making animations showing the vibration modes of the system


# Project4 : Identify an industrial motion system using experimental data

Description -

![MSD 2](https://github.com/PrateekGarg2309/Projects/assets/133784841/81244c7d-97e4-4471-bc07-b901ea4a2641)

The model considered in this part is the more complicated version of the Wirebonder X-Stage. The position of the x-stage is measured 
using encoders. The x-stage should follow a reference trajectory. To identify dynamics, the response of the system was measured 
in a closed loop. Figure presents a block diagram of the control system. A disturbance signal 𝑓 are used and signals 𝑢, 𝑥, 𝑒 were measured.
The obtained measurements are included in the file ClosedLoopSignals.mat. The data file contains
signals in the order of [f, u, x, e]. A zero reference was used to measure the provided data. The sampling
frequency used is given as 8000 Hz.

Steps Involved -

1. Plotting the provided signals in the time domain
2. Calculating and present the closed-loop frequency responses from input disturbance 𝑓 to 𝑢, and
𝑥, respectively. 
3. Calculating and present the frequency response of the plan
4. Computing the transfer function from u to x, to directly estimate the plant model and compare
your results with results obtained
5. Calculate and present the frequency responses of the controller (C) used in the experiments


# Project5 : Compliant Mechanism Design

Description -

![Compliant](https://github.com/PrateekGarg2309/Projects/assets/133784841/1367da25-8ed2-43cb-ba8e-c46354416c03)

When keys or a metal object drop into a gully, they are most of the time retrievable using a hook or a magnet. This
is not the case with plastic cards. This research focuses on the gripping part and leaves the rotating part out of the scope. From
three concepts, one is chosen and developed. The design is then modelled theoretically by doing kinematics and kinetic analysis
on the mechanism. A pseudo-rigid body model and a finite element analysis are then applied to obtain theoretical results
from the design. From the theoretical model a prototype was made and tested to obtain data to compare with the theoretical
data. The PRB model was done in MATLAB using the mathematical equations and visualization was performed as well to check for the 
feasability of the project. The visualization showed that the gripper is able to apply the required amount of force on the card 
to pick it up using actuation. 





