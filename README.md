<center>LTSpice Simulation of a COMS CIRCUIT </center><br><br><br>
#1.AIM<br><br>
To analyse the DC operating point,Transient responce and AC analysis of a CMOS-based circuit using LTspice.<br><br>
#2.COMPONENTS REQUIRED AND THEIR ROLLS<br><br>
1.R<sub>d</sub> (Drain Resistor)<br>
- Provides the required voltage drop to amplify the signal.<br>
- R<sub>d</sub> = 1K&Omega<br>
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
#3.CIRCUIT DIAGRAM<br><br>
<img width="411" alt="circuit_diagram png" src="https://github.com/user-attachments/assets/52b78125-900e-42be-91a6-02bb75e9f72c" /><br><br>
#4.PROCEDURE<br><br>
1.Firstly connect the V<sub>dd</sub> = 1.8V to NMOS drain and ground the source.<br>
2.Apply a 0.9V sine wave at the gate as input.<br>
3.Place the R<sub>d</sub> = 1K&Omega between the drain and output node.<br>
4.Measure the output across R<sub>d</sub><br>
5.Analyse DC operating point,Transfer analysis and AC analysis.<br>







































