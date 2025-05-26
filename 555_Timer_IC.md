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

 ## INFERENCE 

From above two cases we can observe that how the output will trigger for each falling edge of the input trigger signal and remains low after cirtain time delay and  until another falling edge occurs and also we can observe that for each falling edge that capacitor start charging and then after completion of time delay again it will start discharging as we can observe from the above two graph of transient analysis. 

# Astable Multivibrator And Monostable Multivibrator Using 555 Timer ICs 

### Block diagram explaination and working of ASTABLE MILTIVIBRATOR 

![image](https://github.com/user-attachments/assets/d8a0bbe8-f972-4e82-8b48-f679c637e6c9)   

the first block of the astable multivibrator is 
### 1.Voltage Divider:
The voltage divider is a critical internal block of the 555 timer IC. It consists of three equal resistors connected in series between VCC. It creates two reference voltage levels:
1/3 × VCC 
2/3 × VCC 

These levels are used by the internal comparators of the 555 timer to control charging and discharging of the timing capacitor.

### Comparators: 

The voltage divider feeds the non-inverting and inverting terminals of the two internal comparators:
Upper comparator checks when capacitor voltage > 2/3 VCC. and When capacitor voltage > 2/3 VCC,then output of comparator goes HIGH which resets the flip-flop and  output will become LOW.
Lower comparator checks when capacitor voltage < 1/3 VCC.When capacitor voltage < 1/3 VCC,then output of comparator goes HIGH and sets the flip-flop and output will become HIGH.

### SR Flip-Flop:
Stores the current state of the output (HIGH or LOW), based on comparator outputs. 
when VC < 1/3 VCC then SR F/F WILL Set by lower comparator then Output goes HIGH

when VC > 2/3 VCC then SR F/F will Reset by upper comparator then Output goes LOW



### Discharge Transistor (NPN – connected to pin 7) 

it Acts like a switch controlled by the flip-flop. 
 it will turn  ON only when output is LOW and then capacitor will discharges through R2  to GND

it will turn OFF when output is HIGH and then capacitor will charges through R1 and R2 


by above all fuction it will continuonsly generates Square wave at output pin

 by Charging and discharging controls HIGH and LOW time

 and Frequency and duty cycle depend on R1, R2, and C values  

### During the Charging Phase:
During the charging phase, the output of the 555 timer is HIGH. The external capacitor charges through the two resistors R1 and R2 in series, from the supply voltage VCC. The voltage across the capacitor increases exponentially.

This charging continues until the capacitor voltage reaches two-thirds of VCC (2/3 VCC). At this point, the upper comparator inside the 555 detects the threshold, and it resets the internal flip-flop, making the output go LOW.

The time taken for the capacitor to charge from 1/3 VCC to 2/3 VCC is calculated using the formula: ton = 0.69*(R1+R2)*C2

### During Discharging Phase:
During the discharging phase, the output of the 555 timer is LOW. The discharge transistor inside the IC (connected to pin 7) turns ON, allowing the capacitor to discharge only through R2 to ground.

The voltage across the capacitor drops exponentially during this time. Once the voltage falls to one-third of VCC (1/3 VCC), the lower comparator triggers and sets the flip-flop, causing the output to go HIGH again and restarting the charging cycle.

The time taken for the capacitor to discharge from 2/3 VCC to 1/3 VCC is given by: toff = 0.69*R2*C2  


# Given question 
Generate a waveform with pulse width of 0.5 ms under different trigger conditions using 555 timer IC.  

## Circuit Design and calculation  



![WhatsApp Image 2025-05-27 at 02 16 32_4e06a040](https://github.com/user-attachments/assets/e13d9902-7e8b-49e9-a63b-38d78cc23404) 

![WhatsApp Image 2025-05-27 at 02 17 00_401b93ea](https://github.com/user-attachments/assets/c5b6df83-4b30-43cf-9179-e3bb0f9945da)  

### Circuit diagram

![image](https://github.com/user-attachments/assets/d3ce0498-3527-48b6-a022-b9e345a75f91) 

### Transient analysis 

connect the circuit as for the given circuit diagram and then run it in transient analsis mode 

## CASE1:
For ton = 0.4 ms and toff = 0.2 ms, Period = 0.5 ms 

![image](https://github.com/user-attachments/assets/ce7d0e4d-5014-4738-a80b-c1bdbd4171c0) 

as we see in the above waveform the First waveform is the output of monostable multivibrator with pulse width of 0.5 ms. and the 2nd one is output of positive clipper circuit and the third one is output of differentiator circuit and lastely is the output of  astable multivibrator. 

## Case 2:
For ton = 0.8 ms and toff = 0.3 ms, Period = 0.5 ms 

![image](https://github.com/user-attachments/assets/91c3f471-844a-4124-a830-c50bf2ae2e0e) 

as we see in the above waveform the First waveform is the output of monostable multivibrator with pulse width of 0.5 ms. and the 2nd one is output of positive clipper circuit and the third one is output of differentiator circuit and lastely is the output of  astable multivibrator. 


## CASE3:

For ton = 0.5 ms and toff = 0.2 ms, Period = 0.5 ms  

![image](https://github.com/user-attachments/assets/7f45e656-95f1-4d65-9732-48247b1942dc)  

as we see in the above waveform the First waveform is the output of monostable multivibrator with pulse width of 0.5 ms. and the 2nd one is output of positive clipper circuit and the third one is output of differentiator circuit and lastely is the output of  astable multivibrator.  

 ## - if toff is > ton then we have to use inverter after the inverter circuit in order to reset before the next pulse.

 

















 














