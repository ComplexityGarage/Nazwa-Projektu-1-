# PFR-magnetic-levitation

Polarity free repulsion (PFR) is a magnetic levitation technique in which one magnet (rotor) is spun around its axis at ~200Hz, and a second magnet (floater) levitates underneath it. One of the main challenges of achieving levitation is placing the floater in the minimum of the potential. Quite often, the floater is immediately ejected, without ever levitating. The main goal of this project is to create a system that can reliably insert the floater in the minimum of the potential, where it can levitate. 

# Tech used

- NdFeB magnets, nickel coated, 1x1x1 cm, 6.3kg holding power
- 12V DC motor
- Arduino Uno
- HW-095 motor driver
- GY-271 QMC5883L magnetometer
- KA3005P programmable DC power supply (30V)

# Setup (levitation)

The setup can be seen in the images below. The motor itself is held by a 3D printed holder. The holder is connected to aluminium frames, which dampen vibrations of the motor. This is essential for stable levitation. The motor rotates at a constant frequency, and is controlled via the HW-095 motor driver. The motor driver is connected to a programmable power supply and arduino. The arduino determines whether the motor is on, and the motor speed scales linearly with voltage on the power supply. ...cm under the motor there is an aluminium plate of dimensions (...cm), which help stabilize the floater via eddy currents.

<img width="375" height="432" alt="20260213_155959" src="https://github.com/user-attachments/assets/3695e9be-dac9-4c5b-a715-774f4b56ab3e" />

<img width="1140" height="328" alt="123" src="https://github.com/user-attachments/assets/10a589a3-cf6e-47d2-b1bc-a622c0917da9" />


# 3D Component Design
The magnet box consists of two parts. The upper part attaches the entire assembly to the motor and features two symmetrically placed screw holes on either side of the bracket. Inside, there is a slot for a $10 \times 10 \times 10 \text{ mm}$ cubic magnet, rotated by 10°. After placing the magnet inside, the entire assembly is secured with three screws.

<img width="375" height="177" alt="Box " src="https://github.com/user-attachments/assets/7ea915e1-be47-4149-970d-e93687241e6a" />

The second box was designed for automatic magnet positioning. Once the stability point is found, it should be lowered, leaving the magnet in a state of levitation. The motor holder features ventilation holes and two screw holes matched to the specific motor being used. It is secured from the top with four screws.

<img width="640" height="360" alt="228" src="https://github.com/user-attachments/assets/5226c03b-5363-4ca7-9406-0a046dc735df" />


# Setup (Insertion system)

The ideal insertion system would be a robot arm, automated to follow a specific path to place the floater in the right spot. We ordered a simple robot arm based on arduino servomotors. However, we saw that the movement axes of the arm were not cartesian, which would make it difficult to find a good path. Furthermore, the arm was not that stable, meaning that it could be unreliable. So given the time constraints, we decided to go for a manually controlled arm, made from aluminium frames. This has potential advantages. The axes are cartesian, making the movements of the arm more intuitive. Also, if there are changes in the system (such as a different motor speed), it is easier to adapt using a manual arm. With a fully automated arm, new tests may have to be done to find the new equilibrium position.
The manual system is shown in the figure below. There are two vertical aluminium frames, which act like the vertical axis. Between these is a short horizontal frame, which acts as the horizontal axis. This horizontal frame can be moved up and down, as the bolts are just loose enough to allow for movement, but tight enough to prevent it from falling. Parallel to the horizontal axis is a longer frame. This arm is attached in two points to the shorter frame, also with loose bolts. This allows for horizontal movement of the arm. 

<img width="325" height="500" alt="20260213_160208" src="https://github.com/user-attachments/assets/1c931f1e-4928-4979-97b6-0502cc5afce0" />


By attaching the a magnet holder to the end of the arm, it should be possible to levitate the magnet without moving your hands close to the motor.


# Magnetic field measurements
We studied the shape of the magnetic field with the hope to discover the potential minimum. We used the GY-271 magnetometer, which measures all three cartesian components. The z-component is vertical. First we used the weaker magnets as a rotor, and then the stronger ones. The results are presented below. The values are not calibrated, but we assume a monotonous relation between the units of the magnetometer and the magnetic field strength, and a zero bias value. Then the location of the minima, maxima and the point where B=0 are accurately represented by this data. It is of course a very rough analysis, so further research is needed to determine the accuracy of our results, and how it relates exactly to the equilibrium position of the floater. 

# Levitation attempts

# Authors

Witold Kamphorst

Paulina Skalik
