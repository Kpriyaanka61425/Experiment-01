# Monostable multivibrator using 555 timer IC .

## Given Qustion

#### Generating the waveforms with the pulse width of 0.5ms using 555 Timer IC. 


## Some infomation about the 555 Timer IC  
This 555 Timer IC is one of the most widely used integrated circuits in electronics,This IC can be commonly used to produce accurate time delays, oscillations It operates based on charging and discharging a capacitor through resistors, controlled by internal comparators and a flip-flop.

The 555 Timer can operate in three major modes
### 1. Monostable Mode 
It will generates a single output pulse when triggeredand also the duration of the pulse is set by a resistor and capacitor.  
and also the pulse width formula is given by
#### Pulse Width (T) = 1.1*R*C

### 2. Astable Mode -
It produces a continuous square wave without any external triggering. 
and the formula is given by 
#### T = (R1+R2)*C while charging the capacitor 

#### T = R2*C while discharging of the capacitor  

### 3. Bistable Mode 
Works like a basic set-reset latch.
One input triggers it ON, another turns it OFF.


## CIRCUIT DIAGRAM AND CALCULATION

![image](https://github.com/user-attachments/assets/967c008c-84f7-4dd6-aaf5-fa3812f71629)  


![WhatsApp Image 2025-05-27 at 00 14 15_aebc1b1f](https://github.com/user-attachments/assets/2c03f979-432d-4db2-9553-e4499cfaafea) 

## Procedure 

- first build the circuit in ltspice as per the circuit diagram as shown in above figure
- and then select the suitable resistor and capacitor values as per your calculation
- and go the configure analysis in that choose transient analysis with required time limit in milli seconds and run it
- the waveforms will be generated on waveform window for this node you have selected in the circuit

  

## CASE:01
## Transient Analysis 

it is used  mainly to verify the generated signals with respect time domain 

<img width="590" alt="image" src="https://github.com/user-attachments/assets/1eb96750-c88b-44ea-980e-6a7a6c43a305" />


in the above image the first waveform represents Trigger input signal and 2nd waveform is signal at capcitor which is connected to 6th pin of the 555 Timer IC of treshold and the last one output waveform signal 

#### from the above waveform we come to know that how the capacitor carges and discharges and also how the output triggers to hugh value according to the each input falling edge of time approximately 0.5ms in the above graph. 

## CASE:02 

for the repeated trigger inputs of PULSE(5 0 0.05m 0 0 0.05m 0.1m) across the trigger input 

![image](https://github.com/user-attachments/assets/9f2373d0-d3c8-4ec6-aed5-1fc016674771) 

 same as first waveform label but by the above image we came to know that for first falling edge of the trigger input the output goes high and also we can observe how the capicitor is charging and discharging according to input trigger 

 














