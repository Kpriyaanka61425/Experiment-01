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

  Basic Circuit Configurations  

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

   <img width="614" alt="image" src="https://github.com/user-attachments/assets/60516adc-ade0-4b51-b55b-e5009089868b" />
   

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

   Frequency Response of Differential Amplifier

   <img width="593" alt="image" src="https://github.com/user-attachments/assets/33837f80-ce93-4781-b361-72291c0050cd" /> 

   A frequency response graph for a differential amplifier typically shows a relatively flat response across a wide range of frequencies,
   with a gradual roll-off at both very low and very high frequencies, appearing as a "bandpass" characteristic on a Bode plot;
   meaning the amplifier amplifies signals within a specific frequency range most effectively, with reduced gain at the extreme ends of the spectrum.

   Key points about a differential amplifier frequency response graph: 
   
  -  mid-band region:
   The most important part of the graph is the flat region in the middle, where the gain is nearly constant across a wide range of frequencies,
    representing the amplifier's optimal operating range.

 -  Cut-off frequencies:
   
     The points where the gain starts to drop significantly at both low and high frequencies are called the "cut-off frequencies" or "3dB points".
    
 - Bode plot representation:
    
   Frequency response graphs for amplifiers are usually displayed on a Bode plot, where the x-axis is the frequency on a logarithmic scale and
   the y-axis is the gain in decibels (dB) on a linear scale.

   Factors affecting the frequency response of a differential amplifier:
   
-  Capacitances within the circuit:
  
  Internal parasitic capacitances in the transistors and wiring contribute to the high-frequency roll-off. 
 - Coupling capacitors:
   
  Capacitors used to block DC voltage while allowing AC signals can influence the low-frequency response. 
  
 - Transistor characteristics: 

  The specific type of transistors used in the differential pair affects the overall frequency response.   

  

  Design differential amplifier for the following specifications Vdd = 2v,p<=1mw,Vicm=1.1v,Vp 0.4v,
     prform the DC analysis and extract the required parameters. 
     

   - DESIGN PART:
                 Given Vdd= 2v,p=1mw,so,
                 Iss = p/v = 1m/2 = 0.5mA.
                 Id = Iss/2 = 0.25mA.
                 Vp = 0.4v,Rss = Vp/Iss  = 0.4/0.5m = 800Ω,
                 Voutcm = Vdd - IdRd
                 rd = (vdd - vo )/Id  = (2-1.1)/0.25m = Rd = 0.36kΩ,
                 Vd >= Vgs -Vth - Vs = 1-0.3666 = 0.634v
                 since Vds = Vd - Vs=  = 0.234v
                 and Vov = Vgs - Vth  = 1-0.4 - 0.366 = 0.234v
                 since Vds = Vov it is in saturation region.


     
   Q1.Differential amplifier circuit with resistor as tail connected between two sources of the common source amplifier.  

   Circuit Diagram:

   <img width="598" alt="image" src="https://github.com/user-attachments/assets/64d8e2bf-03ef-47cb-9ad0-7a4236928e87" />  

   Components Required:
   - Rd with 3.5Ω

   


   

     

   


   

   

  
 
