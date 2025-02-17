<center>LTSpice Simulation of a COMS CIRCUIT </center><br><br><br>
 1.AIM <br><br>
To analyse the DC operating point,Transient responce and AC analysis of a CMOS-based circuit using LTspice.<br><br>
2.COMPONENTS REQUIRED AND THEIR ROLLS<br><br>  

| Parameter Name | Role |
|:------------------:|:--------------------------------:|
| Rd (Drain Resistor) | Provides the required voltage drop to amplify the signal. <br> Rd = 1KΩ |
| Vd (Drain Supply Voltage) | Provides DC biasing for the NMOS transistor. <br> Vd = 1.8V |
| W (Transistor Width) | Affects the transconductance, influencing gain and bandwidth. <br> W = 203nm |
| MOSFET | CMOSN (TSMC 180nm NMOS transistor) <br> Length = 180nm <br> Threshold Voltage = 0.366V |
| AC Input (SINE source) | To test the signal used to analyze circuit response. <br> DC Voltage = 0.9V <br> Amplitude = 50mV <br> Frequency = 1KHz | 


3.CIRCUIT DIAGRAM<br><br>
<img width="275" alt="circuit_Diagram" src="https://github.com/user-attachments/assets/d350b242-8832-4f79-a2a2-2d2391ef7b72" /><br><br> 

4.PROCEDURE<br><br>
1.Firstly connect the V<sub>dd</sub> = 1.8V to NMOS drain and ground the source.<br>
2.Apply a 0.9V sine wave at the gate as input.<br>
3.Place the R<sub>d</sub> = 1K&Omega; between the drain and output node.<br>
4.Measure the output across R<sub>d</sub><br>
5.Analyse DC operating point,Transfer analysis and AC analysis.<br><br> 

<ins>DC Simulation</ins><br>
<img width="640" alt="DC_oparating_point" src="https://github.com/user-attachments/assets/cfc678e3-5112-4f85-948f-8732ca948def" /><br>
From the simulation: V<sub>in</sub> = 0.9V, r<sub>d</sub> = 1K&Omega;.<br>
If the power dissipation is 100&mu;W across the resistor,then the current through the resistor is given by,<br>
I<sub>d</sub> = Power/Voltage = 100&mu;/1.8 = 5.55*10^-5<br>
The output equation is given by <br>
V<sub>out</sub> = V<sub>dd</sub> - (I<sub>d</sub> * R<sub>d</sub>)<br>
V<sub>out</sub> = 1.8 - ((5.55*10^-5)*(1000)) = 1.7445V<br><br>
Since the calculated current does not match the simulated value,maintain the MOSFET length at 180nm and adust the width to achive the desired current value.<br><br>     

| Length (m) | Width (m) | I<sub>d</sub> (A) |
|----|------|--------|
| 180n | 100n | 4.81×10^-5 |
| 180n | 175n | 5.27×10^-5 |
| 180n | 200n | 5.524×10^-5 |
| 180n | 203n | 5.55×10^-5 |     

<br><br>
The operating point analysis confirms that the NMOS transistor operates in the saturation region with I<sub>d</sub> = 5.55*10^-5A<br>
V<sub>ds</sub> = V<sub>d</sub> - V<sub>s</sub> = 1.7445 - 0 = 1.7445V.(since V<sub>out</sub> = V<sub>d</sub> in given above circuit)<br>
V<sub>ov</sub> = V<sub>gs</sub> - V<sub>tn</sub> = 0.9 - 0.366 = 0.534V.<br>
i.e V<sub>ds</sub> > V<sub>ov</sub>, So,the above circuit is in the saturation region.<br><br>
<ins>Transient Analysis</ins><br><br>
Transient analysis is a time-domain simulation technique used to observe the circuit response to time varying inputs.<br>
For this experiment find the gain and output impendence of the circuit.For the same circuit,perform the transient analysis keeping the sinusoidal voltage signal<br>
DC offset as 0.9V,and amplitude 50mV,and frequency as 1V.<br>
In the configure analysis select stop time as 3ms.<br><br>
<img width="639" alt="transient_analysis" src="https://github.com/user-attachments/assets/1853f4ae-215c-4ca4-85b9-3c567d675183" /><br><br>
From the graph :<br>
We can observe 180° phase shift in the amplified output voltage wave.<br>
gain = V<sub>out</sub>/V<sub>in</sub><br>
gain = 1.7445/50m = 34.89 V/V.<br>
From the calculations:g<sub>m</sub> = 2(I<sub>d</sub>)/(V<sub>ov</sub>).<br>
 = 2*5.55*10^-5/0.534 = 2.0786*10-4 Siemens.<br>
 R<sub>out</sub> = r<sub>d</sub> = 1K&Omega;.<br>
 Overall gain:A<sub>v</sub> = -g<sub>m</sub>*R<sub>out</sub>.<br>
 A<sub>v</sub> =-34.89*1000 = -34890<br><br>
 <ins>AC Analysis</ins><br><br>
 In this experiment ,we will conduct an AC analysisto evaluate the frequency response of the circuit ,<br>
 including parameters such as gain,output impendance ,and output impedance and phase shift .By applying a small-signal <br>
 AC input ,we can access how it behaves under varying frequencies.<br><br>
 For the same circuit ,in the configure analysis select decade as type of sweep,with starting frequency of 0.1Hz to stop frequency as 1THz.<br><br>
 <img width="959" alt="AC_analysis" src="https://github.com/user-attachments/assets/72ba7142-114e-4085-bce5-646b16946193" /><br><br>.
 From the AC analysis graph we obtained gain as 2db and the frequency is 408.83MHz.<br><br> 
 <ins>5.INFERENCE</ins><br><br>
 - from DC analysis we got the operating point I<sub>d</sub> = 5.55*10^-5 ,and we got V<sub>ds</sub> as 1.7445 which grater than the V<sub>ov</sub><br>
 By this we conclude that te given above circuit operates in saturation region.<br>
 - And then from the Transient analysis i have observed the 180° phase shift confirms that the circuit functions as a CMOS inverter. This phase shift occurs because the <br><br>NMOS transistor switches the output to the opposite state of the input. When the input is high, the NMOS conducts, pulling the output low, and vice versa. This <br> behavior validates the inverting property of the CMOS inverter.<br>
 - And from the AC analysis the graph shows the intersection of two lines at -9.277db gain and  210.044GHz of frequency. This intersection point typically represents the cutoff frequency or the -3dB point, where the gain begins to decrease with increasing frequency.<br><br><br><br><br>


 
 <center>LTSpice Simulation of a COMS CIRCUIT -02 </center><br><br><br>
 1.AIM <br><br>
To analyse the DC operating point,Transient responce and AC analysis of a CMOS-based circuit using LTspice.<br><br>
2.COMPONENTS REQUIRED AND THEIR ROLLS<br><br>  

| Parameter Name | Role |
|:---------------------:|:-----------------------------------------------------:|
| Vd (Drain Supply Voltage) | Provides DC biasing for the NMOS transistor. <br> Vd = 1.8V |
| W (Transistor Width) | Affects the transconductance, influencing gain and bandwidth. <br> W = 1000nm (For the CMOSP) <br> W = 210nm (For the CMOSN) |
| MOSFET | Model:CMOSN (TSMC 180nm NMOS transistor) <br> Length = 180nm <br> Threshold Voltage = 0.366V <br>Modle: CMOSP (TSMC 180nm PMOS transistor) <br> Length = 180nm <br> Threshold Voltage = -0.3906V |
| AC Input (SINE source)| To test the signal used to analyze circuit response. <br> Bias Voltage = 0.48V <br> DC Voltage = 0.9V <br> Amplitude = 50mV <br> Frequency = 1KHz | 


3.CIRCUIT DIAGRAM<br><br>
<img width="263" alt="image" src="https://github.com/user-attachments/assets/ee355efd-0f4b-4fcb-a5af-a204e1509952" /><br><br>
<ins>4.PROCEDURE</ins><br><br>
1.Firstly connect the V<sub>dd</sub> = 1.8V to PMOS source and ground the source of NMOS.<br>
2.Apply a 0.9V sine wave at the gate as input  to NMOS mosfet and set the DC bias voltage as gate voltage for PMOS mosfet.<br>
3.connect the V<sub>out</sub> in drain of PMOS and NMOS as shown in figure.<br>
4.Measure the output across v<sub>out</sub><br>
5.Analyse DC operating point,Transfer analysis and AC analysis for the above circuit.<br><br>
<ins>DC Simulation</ins><br>  

<img width="842" alt="image" src="https://github.com/user-attachments/assets/c9aca0da-2bcf-408a-bc5e-05e17d186bde" /> 

From the simulation: V<sub>in</sub> = 0.9V, V<sub>dd</sub> = 1.8V.<br>
If the power dissipation is 100&mu;W across the mosfet,then the current through the resistor is given by,<br>
I<sub>d</sub> = Power/Voltage = 100&mu;/1.8 = 5.55*10^-5A.<br> 
V<sub>out</sub> = 1.40139V.(From the DC operating point simulation ) 
To maintain the MOSFET length at 180nm and adust the width to achive the desired current value,we have simulated as below table shows.  
<br>
| Length (180nm) | Width1 | Width2 | I_D (A) |
|:--------------:|:------:|:------:|:---------:|
| 180nm | 300n | 200n | 4.79*10^{-5} |
| 180nm | 380n | 190n | 5.04*10^{-5} |
| 180nm | 480n | 240n | 5.63*10^{-5} |
| 180nm | 540n | 223n | 5.5*10^{-5} |    
For this  above circuit V<sub>d</sub> = V<sub>out</sub> = 1.401V(For both the mosfets). 
V<sub>gd</sub> = V<sub>g</sub> - V<sub>d</sub>. 
V<sub>gd</sub> = 0.48 - 1.401 = -0.921V.(for PMOS circuit). 
V<sub>gd</sub> = 0.9 - 1.401 = -0.501.(For the NMOS circuit). 
V<sub>gd</sub> > V<sub>tp</sub> (For the PMOS) 
V<sub>gd</sub> <  V<sub>tp</sub> (For the NMOS) 
From the above we conclude that the whole circuit is in the saturation region   


TRANSIENT ANALYSIS   
Transient analysis is a time-domain simulation technique used to observe the circuit response to time varying inputs.<br>
For this experiment find the gain and output impendence of the circuit.For the same circuit,perform the transient analysis keeping the sinusoidal voltage signal<br>
DC offset as 0.9V,and amplitude 50mV,and frequency as 1V.<br>
In the configure analysis select stop time as 3ms.<br><br>  

<img width="839" alt="image" src="https://github.com/user-attachments/assets/3aae9efc-6b55-4335-a6c8-31c150eb5cbc" />  

From the graph :<br>
We can observe 180° phase shift in the amplified output voltage wave.<br>
gain = V<sub>out</sub>/V<sub>in</sub><br>
gain = 1.401/50m = 28.02 V/V.<br> 
From the calculations:g<sub>m</sub> = 2(I<sub>d</sub>)/(V<sub>ov</sub>).(sinse V<sub>ov</sub> = o.534(NMOS) and 1.71(PMOS))<br>
 = 2*5.55*10^-5/0.534 = 2.0786*10-4 Siemens(For NMOS).<br> 
 = 2*5.55*10^-5/1.71 = 6.4912*10-5 Siemens(For NMOS).<br>   

 <ins>AC Analysis</ins><br><br>
 In this experiment ,we will conduct an AC analysisto evaluate the frequency response of the circuit ,<br>
 including parameters such as gain,output impendance ,and output impedance and phase shift .By applying a small-signal <br>
 AC input ,we can access how it behaves under varying frequencies.<br><br>
 For the same circuit ,in the configure analysis select decade as type of sweep,with starting frequency of 0.1Hz to stop frequency as 1THz.<br><br>  

 <img width="838" alt="image" src="https://github.com/user-attachments/assets/b4c331ce-f3f7-4b83-bcf3-b3cf633f42a7" />   

 From the graph of AC analysis we obtained the gain as 5db and frequency as 145.064MHz.   
 <ins>5.INFERENCE</ins><br><br> 
 
 - from DC analysis we got the operating point I<sub>d</sub> = 5.55*10^-5 ,and we got V<sub>gd</sub> as we did the calculations in the DC operating point.<br>
 By this we conclude that te given above circuit operates in saturation region.<br>
 - And then from the Transient analysis i have observed the 180° phase shift confirms that the circuit functions as a CMOS inverter. This phase shift occurs <br>
   because the MOSFET transistor switches the output to the opposite state of the input. When the input is high, the NMOS conducts, pulling the output low, and vice versa.  
   This behavior validates the inverting property of the CMOS inverter.<br>
 - And from the AC analysis the graph we obtained gain in db and frequency in MHz, where the gain begins to decrease with increasing frequency.<br><br><br><br><br>

 

 





 














 
 
 


 








