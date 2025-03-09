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
   -  a differential amplifier receives two input signals that are equal in magnitude but opposite in phase, meaning Vin1=−Vin2. This results in a nonzero differential input voltage (Vin1−Vin2 ), which the amplifier effectively amplifies.
![Screenshot 2025-03-03 015718](https://github.com/user-attachments/assets/cc7313bf-4fa6-426e-a7c7-2306b8d5031b)


Since the circuit is symmetrical, the total tail current (ISS) remains constant, but it is redistributed between the two transistors based on the input difference. When Vin1 increases,M1 conducts more current while M2 conducts less, and vice versa. This imbalance creates a differential output voltage (𝑉𝑜𝑢𝑡=𝑉𝑜1−𝑉𝑜2n), which is the amplified version of the input difference. The gain in this mode, called differential gain (Ad), is given by 𝐴𝑑=(𝑉𝑜1−𝑉𝑜2)/(𝑉𝑖𝑛1−𝑉𝑖𝑛2)Ad=(Vo1−Vo2)/(Vin1−Vin2) and is typically high. This mode is crucial for signal amplification while rejecting common-mode noise and interference, making differential amplifiers ideal for precise, low-noise applications like sensor interfaces and communication systems.
- Common-Mode: The same signal is applied to both inputs.Ideally, the output should be zero,
   but practical amplifiers exhibit some small common-mode gain.
   - common-mode signals refer to identical input voltages applied to both transistors, meaning 
   𝑉𝑖𝑛1=𝑉𝑖𝑛2Vin1=Vin2, resulting in a differential input voltage of zero (𝑉𝑖𝑛1−𝑉𝑖𝑛2=Vin1−Vin2=0).

   <img width="510" alt="image" src="https://github.com/user-attachments/assets/8d29b64b-78f7-41cb-8a3c-36bb34a81754" />

 
   Due to the symmetry of the circuit, where both transistors and drain resistors are identical, the drain currents remain 
   equal (𝐼𝐷1=𝐼𝐷2=𝐼𝑆𝑆/2ID1=ID2=ISS/2), leading to identical output voltages. As a result, the differential output becomes 
   zero, effectively rejecting the common-mode signal. This property allows the amplifier to eliminate noise and unwanted DC 
  offsets without needing external capacitors, making it efficient and space-saving. Ideally,
  the common-mode gain (𝐴𝑣=(𝑉𝑜1−𝑉𝑜2)/𝑉𝑖𝑐𝑚Av=(Vo1−Vo2)/Vicm) should be zero, meaning no common-mode signal should appear at 
  the output.
   

  Design differential amplifier for the following specifications Vdd = 
  2v,p<=1mw,Vicm=1.1v,Vp 0.4v,
  prform the DC,transfer and AC analysis and extract the required parameters.  

     
     

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


     
   Q1.Differential amplifier circuit with resistor as tail connected between two sources of the common source amplifiers.  

   Circuit Diagram: 
   

   <img width="644" alt="image" src="https://github.com/user-attachments/assets/cea6a71e-b8fe-45da-867d-d7730dc2ab66" />

 
   

   Components Required: 

   - (Rd)Drain Resistor with 3.5Ω
   - 2CMOSN mosfets with lenth = 180n and width  = 23µ
   - and also Rss resistor of 800 Ω
   - after all connect the circuit with respect to given circuit design

     
Procedure : 
   
   - forstly go the ltspice of file then choose the new shcematic then continue building the circuit
   - as for the circuit first from the components bar search for nmos4 and plce it two types then connect the three voltage sources
     as Vdd ,Vincm1 and Vincm2 with given specific value
   - and then using wire commond make connection as for the diagram and then lastly sources of two identical mosfets will join
     then we hav connect the Rss resistor as tail of those two sources as shown in circuit diagram.
  - and to do the DC ananlysis choose for Dc operating point to adjust the mosfets specific value
  - then after go for Transient Ananlysis with stop tyme of 5m or 3m. by this we can calculate gain 
  - then by choosing the Ac analysis we can find the small signal gain and  and we get to know up to  what frequency it can operate.
    

 DC analysis: 


   <img width="443" alt="image" src="https://github.com/user-attachments/assets/f54aeea7-97e4-479b-9cc5-6b5dd0945718" /> 

   The above diagram shows the design values of the mosfet
   and to conform the each mosfet is in saturation we go with this below circuit 

   <img width="431" alt="image" src="https://github.com/user-attachments/assets/13afecec-fc68-4be7-a391-0bd5e9c23e75" /> 

   by the above graphs value we can calculate whether the mosfet is in saturation or not 
   since Vgs1 = 0.59 ,Vov = Vgs - Vth = 0.59 - 0.497 = 0.093v ,Vgd = 1 - 1.1 = 0.6 
   since Vds>=Vov and Vgd <=Vth so we can conclude CMOS1 is in saturation and also similarly CMOS2 also will be in satuaration   


   TRANSIENT Analysis 


   <img width="959" alt="image" src="https://github.com/user-attachments/assets/5665b0fd-e3f9-4275-9757-9ac367ce41ac" />
 

   since the gain = Vout/Vin = 9.1468v/v 

   AC Analysis  

   <img width="959" alt="image" src="https://github.com/user-attachments/assets/d722552e-2bcf-403f-89fc-82c41a8b9834" />
  

   Av = 20db 
   and the frequency for 3db is 3.484GHz

   Input Swing:  

   
   <img width="959" alt="image" src="https://github.com/user-attachments/assets/e6738d0c-7a12-4ca5-b7de-35703d254878" />


   Input maximum swing is given by avarage of Vincmmin and Vincmmam 
   so,Vincmmim = Vth + Vov1  = 0.497 + 0.093 = 0.59v
   and Vincmmax = Vdd - IdRd +Vth = 1.622v
   and Vincmswing = (1.662+0.59)/2 = 1.106v


   INFERENCE 

   - The DC analysis shows that the MOSFETs operate in saturation with balanced drain currents when input voltages are equal.
   - The transient response confirms proper differential behavior by 180 degree phaseshift.
   - The AC analysis indicates moderate gain,3db gain and common-mode rejection.


    
   Q2.By Replaceing the resistor with constant current source 



   Circuit Diagram: 

   <img width="587" alt="image" src="https://github.com/user-attachments/assets/40b5d478-96a3-4f0b-97e9-29ccc390ab9a" />


   DC analysis : 
   

   ![Screenshot 2025-03-02 235618](https://github.com/user-attachments/assets/1ec590ce-68a5-4775-851b-125ebb2e7c6a)  


   ![Screenshot 2025-03-02 235658](https://github.com/user-attachments/assets/2358d817-ba7d-4b96-bd3d-38e5db646146)  

   by the above graphs value we can calculate whether the mosfet is in saturation or not 
   since Vgs1 = 0.59 ,Vov = Vgs - Vth = 0.59 - 0.497 = 0.093v ,Vgd = 1 - 1.1 = 0.6 
   since Vds>=Vov and Vgd <=Vth so we can conclude CMOS1 is in saturation and also similarly CMOS2 also will be in 
   satuaration



   TRANSIENT Analysis 


   ![Screenshot 2025-03-03 001109](https://github.com/user-attachments/assets/4f9e1f39-f001-46e6-8755-f45e60e4b0c2)  

   since the gain = Vout/Vin = 8.306v 


   Ac analysis 

   ![Screenshot 2025-03-02 235200](https://github.com/user-attachments/assets/12069669-20b7-4bb2-92ed-15d2bfc594f6)  

  
   Av = 20db 
   and the frequency for 3db is 3.484GHz


   Input Swing 


   ![Screenshot 2025-03-03 000050](https://github.com/user-attachments/assets/b9388d38-f57f-48a8-b250-41b826850335)  

   Input maximum swing is given by avarage of Vincmmin and Vincmmam 
   so,Vincmmim = Vth + Vov1  = 0.497 + 0.093 = 0.59v
   and Vincmmax = Vdd - IdRd +Vth = 1.622v
   and Vincmswing = (1.662+0.59)/2 = 1.106v  

   INFERENCE  
   
   - Replacing the resistor with a current source improves bias stability, as seen in the DC analysis.
   - The transient response is more stable, ensuring better symmetry.
   - The AC analysis shows increased gain and bandwidth compared to Circuit-1.



   Q3.concant current source replace with mosfet   

   <img width="617" alt="image" src="https://github.com/user-attachments/assets/143523e6-ad5d-4d70-ab19-34ca0b605f35" />
  

   

   DC Analysis 

   <img width="455" alt="image" src="https://github.com/user-attachments/assets/dc14de9a-5bee-40b4-8ad3-c54c4549f856" />  

   <img width="435" alt="image" src="https://github.com/user-attachments/assets/6414fded-b4a4-4baa-a6e0-781fc482260e" /> 


   
   by the above graphs value we can calculate whether the mosfet is in saturation or not 
   since Vgs1 = 0.588v,Vds = 0.711 ,Vov = Vgs - Vth = 0.588 - 0.497 = 0.091v ,Vgd = 1 - 1.1 = 0.6 
   since Vds>=Vov and Vgd <=Vth so we can conclude CMOS1 is in saturation and also similarly CMOS2 also will be in 
   satuaration because CMOS2 is the identicle to CMOS1.
   Now we will see whether the CMOSN3 is in saturation or not  
   since Vgs1 = 0.896v,Vds = 0.412 ,Vov = Vgs - Vth = 0.896 - 0.497 = 0.399v ,Vgd = 0.896 - 0.4 = 0.496
   since Vds>=Vov and Vgd <=Vth so we can conclude CMOS3 is also in saturation 

   
   TRANSIENT Analysis


  <img width="959" alt="image" src="https://github.com/user-attachments/assets/68bace4b-d9a2-4306-90e1-9712b5fff9c4" />
  

  since the gain = Vout/Vin = 0.8.522v/v .


  AC Analysis 

  <img width="959" alt="image" src="https://github.com/user-attachments/assets/5af5c8ae-d50a-46de-aeb3-9b91e79fd1a8" />
 
   Av = 20db 
   and the frequency for 3db is 3.484GHz 
   

  Input swing 

  <img width="959" alt="image" src="https://github.com/user-attachments/assets/2fba1128-47a7-4014-9169-cf8c1bfb6aac" />


   Input maximum swing is given by avarage of Vincmmin and Vincmmam 
   so,Vincmmim = Vth + Vov3   = 0.896 v
   and Vincmmax = Vdd - IdRd +Vth = 1.622v
   and Vincmswing = (1.662+0.896)/2 = 1.259v 

   by this above input swing we can observe the clip in the output wave as shown above. 

   INFERENCE 

   - The DC analysis confirms that the MOSFET-based current source regulates the tail current effectively.
   - The transient response maintains signal accuracy with improved performance.
   - The AC analysis shows higher gain and bandwidth.
   - The DC sweep analysis validates expected output variations.


Q4..Differential amplifier circuit with Drain connected PMOS and NMOS Mosfet as tail connected between two sources of the common source amplifiers  

DC Analysis 

<img width="457" alt="image" src="https://github.com/user-attachments/assets/1f4893cf-847f-4402-bd52-61940a98c559" />

 
<img width="454" alt="image" src="https://github.com/user-attachments/assets/7ab37c70-2695-4406-b299-107e98e61003" />


By te above information we can calculate the each mosfet is in saturation region or not. 
 - Since the two PMOS drain connected mosfets will always be in saturation. 
 - for mosfets of common sourse amplifiers which are identicle to each other
   Vov = 0.085v,Vds = 0.688v, and VGD = 1-1.12 = 0.12v
   since Vds >= Vov and VGD <= Vth so both are in saturation region
 - for the tail Mosfet Vov = 0.422v,Vds = 0.433v , VGD = 0.897-0.432 = 0.465v
   since the Vds >= Vov and VGD <=Vth ,so tail mosfet is also in the saturation region.


TRANSIENT ANALYSIS 


     



   












   
   



   


   

     

   


   

   

  
 
