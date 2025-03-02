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

  - Single-Ended Differential Amplifier:

    <img width="293" alt="image" src="https://github.com/user-attachments/assets/cac43992-68ef-480b-927c-d94d89971e46" />
    
    This refers to a differential amplifier where only one output is taken, even though
    it might have two input signals, often with one input grounded.
    Provides moderate common-mode noise rejection.
    Common in low-cost amplifier circuits.
  - Double-Ended Differential Amplifier:

    <img width="416" alt="image" src="https://github.com/user-attachments/assets/92c8e41c-157b-49b7-828d-244fc201783d" />
    

    This is a full differential amplifier, meaning both inputs are used and both outputs
    are utilized, providing a balanced differential signal.
    Offers higher noise immunity and common-mode rejection.
    Used in high-precision circuits.
 - Differential amplifier with active load:

   In this configuration, instead of a passive resistor as the load in the common source circuit
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

  
   Input and Output Characteristics

   A typical differential amplifier input-output waveform would show two identical sinusoidal
   waveforms on the input channels (V1 and V2) with a small voltage difference between them,
   and on the output, a single sinusoidal waveform with an amplitude proportional to the difference
   between the input voltages (V1 - V2), effectively "canceling out" any common-mode noise present on both inputs

   Key points about the waveform:
   
   Two input signals:
   A differential amplifier has two input channels (V1 and V2) which are typically shown as identical sinusoidal
   waveforms with a small voltage difference between them, representing the differential signal that the amplifier
   is designed to amplify.
   
   Output signal:
   
  The output waveform is a single sinusoid with an amplitude proportional to the voltage difference between the two  
  input signals (V1 - V2), meaning if the input signals are almost identical, the output will be very small.  
  
  Common-mode rejection: 
  
   A key feature of a differential amplifier is its ability to reject common-mode noise, which is a signal present on 
   both input channels simultaneously. This is illustrated by the fact that even if significant noise is added to both  
   input signals, the output will only reflect the difference between them.  
   
   Important considerations: 
   
   Phase relationship: 
   
   Depending on the circuit design, the output waveform may be in phase with the positive input signal (V1) or inverted relative to it.   
   
   Gain: 
   The amplitude of the output waveform is determined by the gain of the differential amplifier, 
   which is typically set by the resistor values in the circuit.

   

  
 
