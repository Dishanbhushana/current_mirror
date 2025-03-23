### current_mirror 
A current mirror consists of at least two transistors (usually bipolar junction transistors (BJTs) or metal-oxide-semiconductor field-effect transistors (MOSFETs)) arranged in such a way that the current flowing through one transistor (the reference transistor) is mirrored by the other transistor(s) (the output transistor(s)).<br>
A MOSFET current mirror works similarly to a BJT current mirror. However, instead of the base-emitter voltage, the MOSFET current mirror relies on the gate-source voltage (Vgs) to establish the current. The gate-source voltage of both MOSFETs in the mirror is set equal, and by matching their dimensions and ensuring proper biasing, the output current in the mirrored transistor will be a copy of the reference current.<br>
## Types of Current Mirrors<br>
#### Simple Current Mirror: This is the basic current mirror configuration, where two transistors are used to mirror the current. It works well for moderate precision but suffers from issues like output impedance and variations due to mismatches in the transistors.<br>
#### Wilson Current Mirror: The Wilson current mirror is a more advanced version that improves output impedance and accuracy by adding additional transistors to provide better current mirroring performance.<br>
#### Cascode Current Mirror: The cascode current mirror uses an additional transistor to improve output resistance and make the current mirror less sensitive to changes in the load. This version has better performance in high-impedance environments.<br>
#### Improved Current Mirrors (e.g., Vbe-multiplier, etc.): These designs attempt to minimize the effects of transistor mismatch, temperature variations, and other real-world imperfections to provide more accurate and stable current mirrors.<br>
## applications of Current Mirrors<br>
#### Biasing: Current mirrors are frequently used to set bias currents in amplifier stages and other analog circuits, ensuring stable and predictable performance.<br>
#### Current Sources: They can act as precise current sources, which are useful in analog signal processing, active filters, and voltage-controlled current sources.<br>
#### Active Loads: Current mirrors are used in differential amplifier stages to provide a high output impedance, making them useful in increasing the gain of the amplifier.<br>
![WhatsApp Image 2025-03-23 at 18 30 48_343ede1a](https://github.com/user-attachments/assets/f082910b-ea01-4ea4-be02-938c394ff747)<br>
## AIM design and analyse the current mirror circuit a a active load in the amplifier circuit<br>
given:VDD=1.8V,P<=1mW,Av=10V/V.<br>
## circuit diagram from LT spice
![Screenshot (50)](https://github.com/user-attachments/assets/a9c65dd1-b5db-4243-b7e5-95e6900e83ea)
## for mirror ratio of1:1<br>
WKT It=Iref+Ix
Therefore, for 1:1 ratio Iref=Ix
So,Iref=It/2
It=P/Vdd
It=1mW/1.8V
It=0.555mA.
Therefore,Iref=0.2778mA.

To obtain the current value according to the given ratio, the provided values of W/L for M1 is 3um/180nm , M2 is 3um/180nm, and M3 is 3um/180nm.
Vin to be in saturation region so considering Vin is 0.838V.
![Screenshot (49)](https://github.com/user-attachments/assets/becad374-ecd4-4490-a57a-cb4e465c8fc3)
### Analyzing the current mirroring circuit by changing the w and L but maintaing the same ratio.

**(a)L=180nm.**

We know the (w/L) ratio is 16.667.

Therefore for L=180nm the w=3um.

|Mosfet     |  Id                 | 
|-----------|---------------------|
|  M1       |   0.000277527       |             
|  M2       |   0.000277527       |         
|  M3       |   0.0002778         |             

**(b)L=500nm.**

We know the (w/L) ratio is 16.667.

Therefore for L=500nm the w=8.334um.

|Mosfet     |  Id                   |  
|-----------|-----------------------|
|  M1       |   0.000281241         |             
|  M2       |   0.000281241         |             
|  M3       |   0.0002778           |   
## Transient Analysis:
Steps for transient Analysis:
Replace DC input with an AC signal.
Use SINE(dc_offset, Amplitude, Frequency).
Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
Set Stop Time: 10ms.
Run the simulation.
![WhatsApp Image 2025-03-23 at 19 55 16_7342edaa](https://github.com/user-attachments/assets/70d6bc30-5316-4baf-8683-08efa3d2f5ff)
Our dc_offset = 0.838V and assume amplitude as 50mV and frequency as 1Khz.
The theriotical gain is-10V/V.But the obtained gain from the circuit is -10.2V/V.

## AC analysis<br>
Steps to get Ac analysis Waveform:
In simulation tab select AC Analysis.
In the AC Analysis tab, select Type of Sweep as Decade.

Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).
![WhatsApp Image 2025-03-23 at 19 55 27_76c09a7e](https://github.com/user-attachments/assets/2f158ad0-6fb9-4d83-853a-cf3575ae0f58)
gain from the AC analysis(frequency response) is 22.16dB <br>
The obatined 3db B.W=2.267GHz.<br>

### circuit_2
It=Iref+Ix
Therefore, for 1:2 ratio 2*Iref=Ix
So,Iref=It/3
It=P/Vdd
It=1mW/1.8V
It=0.555mA.
Therefore,Iref=0.185mA<br>
according to the given ratio, the provided values of W/L for M1 is 6um/180nm , M2 is 6um/180nm, and M3 is 3um/180nm,Vin is 0.763V.<br>
### circuit diagram
![Screenshot (48)](https://github.com/user-attachments/assets/9eb53086-1544-4826-81fb-3bb68db6fb20)
### DC analysis:
![Screenshot (51)](https://github.com/user-attachments/assets/26a2b4e3-f99e-4de7-8c6a-88877ddf47ce)
### Transient Analysis:<br>
Steps for transient Analysis:
Replace DC input with an AC signal.
Use SINE(dc_offset, Amplitude, Frequency).
Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
Set Stop Time: 10ms.
Run the simulation.
![WhatsApp Image 2025-03-23 at 19 57 35_935a16c6](https://github.com/user-attachments/assets/2e6b6d6a-bd8e-4148-a8d3-d7a6849ed85d)
Our dc_offset = 0.763V and assume amplitude as 50mV and frequency as 1Khz.<br>
gain is -10V. obtained gain from thecircuit is -11.68V/V.<br>
### Ac analysis 
In simulation tab select AC Analysis.<br>
In the AC Analysis tab, select Type of Sweep as Decade.<br>
![WhatsApp Image 2025-03-23 at 19 57 44_ac3f2335](https://github.com/user-attachments/assets/a7e5c43c-2a0e-4397-8544-12b3215e1c07)
Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).<br>
Expected gain in db of the circuit is 21.34db.But the obtained gain from the AC analysis(frequency response) is 24.6dB.<br>
### **Table:**
| **Parameter**  | **Mirror Ratio 1:1** (Theory) | **Mirror Ratio 1:1** (Practical) | **Mirror Ratio 1:2** (Theory) | **Mirror Ratio 1:2** (Practical) |
|---------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------|
| Av (in dB)    | 20 dB                        | 22.16 dB                     | 21.34 dB                     | 24.6 dB                     |
| Av (in V/V)   | 10                           | 10.2                          | 10                           | 11.68                         |
| 3 dB Bandwidth | -                            | 2.267 GHz                     | -                            | 1.173 GHz 
### PART-B
## Aim
Design the differential amplifier using the same design specification as Experiment-3. Perform DC analysis,trasient and AC analysis.<br>
![Screenshot (52)](https://github.com/user-attachments/assets/53db9b16-b38a-4dd3-bc60-bf182207723e)
### DC operating point<br>
![Screenshot (53)](https://github.com/user-attachments/assets/e6d38b0f-bb0c-4cb5-a6f1-744276324ea8)
### Transient analysis<br>
![Screenshot (54)](https://github.com/user-attachments/assets/b9c35ff9-5cad-4d64-9c73-b20876b756c5)
### AC analysis<br>
![WhatsApp Image 2025-03-23 at 21 38 42_6c93ae30](https://github.com/user-attachments/assets/9d0633a1-de0f-4e91-8859-70b3e653bd01)
### 3dB
![WhatsApp Image 2025-03-23 at 21 38 52_0b26fd2a](https://github.com/user-attachments/assets/4038e5ba-6049-41e0-9521-e6d178aef3fa)
## Inference<br>
A current mirror circuit essentially copies the current flowing through a reference transistor (or current source) to another transistor, which is typically part of the output stage. By doing so, it provides a controlled current for applications where precise current regulation is required. 
The current mirror circuit effectively replicates the reference current with minimal deviation, ensuring accurate current mirroring across different W/L ratios.
As the W/L ratio changes but the ratio itself remains constant, the drain current (Id) values stay nearly the same, confirming the mirror circuit's functionality.
The amplifier gain is slightly higher than the theoretical predictions in both mirror ratios, suggesting small discrepancies possibly due to transistor parameter mismatches or simulation artifacts.
Increasing the mirror ratio (from 1:1 to 1:2) results in a higher gain, as expected, but also reduces the bandwidth from 2.267 GHz to 1.173 GHz.
Overall, the obtained results are in close agreement with theoretical values, affirming both the simulation setup and the circuit's performance.




 















