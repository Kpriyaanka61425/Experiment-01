   EXEPERIMENT NO-06
   DESIGN AND ANALYSIS OF CURRENT MIRRORS CIRCUITS  


   In this current mirror circuits we use the reference current source known as Iref(Golden Reference Current Source)
   designed by Bandgab Reference circuit,which mainly used to copy the reference current into another branch of the circuit with high accuracy. 


  NEED OF USING CURRENT MIRROR INSTEAD OF USING VOLTAGE SOURCE TO BIAS ANY MOSFET

  | **Aspect** | **Current Mirror Biasing** | **Voltage Source Biasing** |
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
voltage will be biased and one more condition we should know while biasing the mosfet is that diode connected mosfet and which will get biased by the reference mosfet both should hae the same Vgs value  and also aspect ratio of both mosftes should also be same then only current mirror occurs perfectly otherwise current mirroring will not occur perfecty.


   
