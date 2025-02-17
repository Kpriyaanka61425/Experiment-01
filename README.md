<center>LTSpice Simulation of a COMS CIRCUIT </center><br><br><br>
1.AIM<br><br>
To analyse the DC operating point,Transient responce and AC analysis of a CMOS-based circuit using LTspice.<br><br>
2.COMPONENTS REQUIRED AND THEIR ROLLS<br><br>
1.R<sub>d</sub> (Drain Resistor)<br>
- Provides the required voltage drop to amplify the signal.<br>
- R<sub>d</sub> = 1K&Omega;<br>
2.V<sub>d</sub> (Drain Supply Voltage)<br>
- Provides DC biasing for the NMOS transistor<br>
- V<sub>d</sub> = 1.8v<br>
3.W (Transistor Width)<br>
- affects the transconductance ,influencing gain and bandwidth<br>
- W = 203nm<br>
4.MOSFET<br>
- CMOSN (TSMC 180nm NMOS transistor)<br>
- length = 180nm<br>
- Threshold Voltage  = 0.366V<br>
5.AC Input (SINE source)<br>
- To test the signal used to analyse circuit response.<br>
- DC Voltage = 0.9v<br>
- Amplitude = 50mV<br>
- Frequency = 1KHz<br>
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
Since th ecalculated current does not match the simulated value,maintain the MOSFET length at 180nm and adust the width to achive the desired current value.<br><br>     

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
 From the AC analysis graph we obtained gain as -9.277db and the frequency is 210.044GHz.<br><br> 
 <ins>5.INFERENCE</ins><br><br>
 - from DC analysis we got the operating point I<sub>d</sub> = 5.55*10^-5 ,and we got V<sub>ds</sub> as 1.7445 which grater than the V<sub>ov</sub><br>
 By this we conclude that te given above circuit operates in saturation region.<br>
 - And then from the Transient analysis i have observed the 180° phase shift confirms that the circuit functions as a CMOS inverter. This phase shift occurs because the <br><br>NMOS transistor switches the output to the opposite state of the input. When the input is high, the NMOS conducts, pulling the output low, and vice versa. This <br> behavior validates the inverting property of the CMOS inverter.<br>
 - And from the AC analysis the graph shows the intersection of two lines at -9.277db gain and  210.044GHz of frequency. This intersection point typically represents the cutoff frequency or the -3dB point, where the gain begins to decrease with increasing frequency.
 
 


 
 





































