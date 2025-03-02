EXPERIMENT -03   
DIFFERENTIAL AMPLIFIER CIRCUITS  



 A differential amplifier is a type of electronic amplifier that amplifies  
 the difference between two input signals and suppresses any signal that is 
 common ON both inputs.This feature makes it highly effective in eliminating 
 noise and interference.It is the fundamental building block of many analog 
 circuits and forms the input stage of most operational amplifiers (op-amps).  

  IMPORTANCE OF DIFFERENTIAL AMPLIFIERS 

- Noise Reduction: By rejecting common-mode noise, they improve signal integrity.
- High Accuracy and Stability: Used in precision measurement and control systems.
- Essential in Op-Amp Design: The core component in operational amplifiers and
  instrumentation amplifiers.
- Wide Range of Applications: Found in communication systems, biomedical devices, 
  and industrial sensors.

  Basic Circuit Configuration  

  A simple differential amplifier consists of two transistors (BJT or MOSFET) with 
  their emitters or sources connected together, sharing a common current source.The 
  differential output can be taken either single-ended or as a fully differential signal.

  Working Principle of a Differential Amplifier

  A differential amplifier operates on the principle of superposition and differential gain.
  The output voltage Vout is given by:
           Vout=Ad(V1−V2)
 Where:
     - Ad is the differential gain of the amplifier
     - V1 and 𝑉2 are the two input voltages
 
  Differential and Common-Mode Operation
  
-  Differential Mode: The two input signals are equal in magnitude but opposite in phase. 
   The amplifier amplifies their difference. 
 - Common-Mode: The same signal is applied to both inputs.Ideally, the output should be zero,
   but practical amplifiers exhibit some small common-mode gain.

  Types of Differential Amplifiers 

  - Single-Ended Differential Amplifier
    This refers to a differential amplifier where only one output is taken, even though
    it might have two input signals, often with one input grounded.
    Provides moderate common-mode noise rejection.
    Common in low-cost amplifier circuits.
  - Double-Ended Differential Amplifier
    This is a full differential amplifier, meaning both inputs are used and both outputs
    are utilized, providing a balanced differential signal.
    Offers higher noise immunity and common-mode rejection.
    Used in high-precision circuits.
 - Differential amplifier with active load:
   In this configuration, instead of a passive resistor as the load in the collector circuit
   of the transistors, an active current source (like another transistor) is used, 
   which Enhances gain and improves signal-to-noise ratio.
   Essential in integrated circuit (IC) op-amps.
 - Differential amplifier with constant current source:
   This design incorporates a constant current source to provide a stable bias current
   for the differential pair, enhancing performance.
   Enhances common-mode rejection ratio (CMRR).
 - Instrumentation amplifier:
   This is a specialized type of differential amplifier designed for high input impedance and
   excellent common-mode rejection, often used in applications where precise measurement of small
   signals is required.

  
 
