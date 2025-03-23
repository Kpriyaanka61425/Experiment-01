   EXEPERIMENT NO-06
   DESIGN AND ANALYSIS OF CURRENT MIRRORS CIRCUITS  


   In this current mirror circuits we use the reference current source known as Iref(Golden Reference Current Source) designed by Bandgab Reference circuit,
   which mainly used to copy the reference current into another branch of the circuit with high accuracy.without using the voltage source to bias the circuit. 


  NEED OF USING CURRENT MIRROR INSTEAD OF USING VOLTAGE SOURCE TO BIAS ANY MOSFET

| | **Current Mirror Biasing** | **Voltage Source Biasing** |
|--------------|----------------------------|----------------------------|
| **Stability** | Provides a stable and precise bias current, independent of supply voltage variations. | Sensitive to supply voltage fluctuations, which can affect circuit performance. |
| **Temperature Dependence** | Less affected by temperature variations when designed properly (e.g., using a bandgap reference). | Can be highly affected by temperature changes due to variations in resistances and transistor parameters. |
| **Process Variations** | More robust against semiconductor process variations, ensuring consistent current across different ICs. | Component variations (e.g., resistors, transistor threshold voltages) can cause inconsistencies in biasing. |
| **Power Efficiency** | Can be designed for low-power applications by scaling current appropriately. | Often requires additional resistors and power dissipation to maintain a stable bias. |
| **Accuracy** | Provides precise current replication, essential for analog and mixed-signal circuits. | Difficult to maintain exact voltage and current values due to component tolerances. |
| **Load Independence** | The mirrored current remains constant regardless of load variations. | Output voltage may change depending on load, leading to unstable biasing. |
| **Integrated Circuit (IC) Suitability** | Ideal for ICs, where matched transistors ensure high accuracy and compact design. | Requires resistors, which take up more space and are harder to fabricate accurately in ICs. |
| **Scalability** | Can easily scale the reference current by adjusting transistor ratios. | Scaling requires changing resistors or additional design modifications. | 

and also we need to check wheather bias voltage is NMOS or PMOS because while biasing the mosfet we will use the same type mosfet to copy the current and also 
we need to check whether the bias mosfet which connected to refernce current should be diode connected because it needs to convert the current to voltage then the coverted
voltage will be biased  and that mosfet will converts the voltage into current,and one more condition we should know while biasing the mosfet is that diode connected mosfet and which will get biased by the reference mosfet both should hae the same Vgs value  and also aspect ratio of both mosftes should also be same then only current mirror occurs perfectly otherwise current mirroring will not occur perfecty.  and also long channel mosfets required for mirroring the current rather than the short channel mosfets.


Q.PART-A 

Design and analyse the current mirror circuit for the following specifications.

Av > -10V/V
Vdd = 1.8V
P <= 1mW
Perform the DC analysis, Transient analysis and AC analysis while maintaining (W/L) same for different values of Length(L). ALso find the maximum output swing and bandwidth. 
cas1:L = 180nm 
case2:L = 500nm 
case3:L = 1µ
DESIGN: 

1. Determine the drain current (Id)

   Id = P/Vdd = 1m/1.8 = 0.555mA

2. Determine the reference current (Iref)

   Iref = Id/2 = 0.555m/2 = 0.277mA


Q1:FOR ASPECT RATIO OF 1:1    
cASE1: L = 180nm
CIRCUIT DIAGRAM:

<img width="581" alt="image" src="https://github.com/user-attachments/assets/5d073b0d-ebd6-4eec-8905-60770341e67b" />    

PROCEDURE:
- first set up the circuit in LTspice as shown above
- and apply the V1/Vdd voltage as 1.8(given),and also apply the V2 value as 0.5v.
- and also apply the current valuve as we have already measured 
- then apply suitable w/l values for the applyed mosfets
- and then go to edit simulation in that DC point and click on the run button then we can verify ouer values.

DC Analysis:   


We will do the dc analysis to determine the circuit is in operating in saturation region or not . 

<img width="387" alt="image" src="https://github.com/user-attachments/assets/def3a2c0-8f8b-4ba8-adc1-2a6e478a4b61" />    

the aspect ratio what i had used
| | **W** | **L**|
|-|-------|------|
| **MOSFET1** | 1.2µ | 180n |
| **MOSFET2** | 1.2µ | 180n |
| **MOSFET3** | 202.8µ | 180n|


<img width="424" alt="image" src="https://github.com/user-attachments/assets/97f3349a-fb08-44f3-9ce1-4140b0a79ad9" />    

TRANSIENT ANALYSIS 

In this analysis we observe the how the circuit behaves with respect to time . 

<img width="959" alt="image" src="https://github.com/user-attachments/assets/9a46c5ec-c5c4-4d9e-83d4-112455f85aee" /> 
<img width="955" alt="image" src="https://github.com/user-attachments/assets/b7243f9c-098f-491c-ac31-1bfaba424efe" />  

- the expected gain is above 10v/v(given in question)
- and obtained value is Av = Voutp-p/3m = 27.8166v/v

AC ANALYSIS:

in this we will observe how the circuit components behaves with frequency. 

<img width="959" alt="image" src="https://github.com/user-attachments/assets/6a93c11b-8294-4ba6-a705-90ad0e02b502" />  

the obtained gain = 22.89db
-3db frequency is 412.308MHz 
| Gain | Theoretical Value | Practical Value |
|---|----|---|
| Av (V/V) | 10 | 27.8166 |
| Av (dB) | 20 | 22.89 | 

FOR Lenth = 500nm 

DC Analysis 






 











   
