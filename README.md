### current_mirror 
A current mirror consists of at least two transistors (usually bipolar junction transistors (BJTs) or metal-oxide-semiconductor field-effect transistors (MOSFETs)) arranged in such a way that the current flowing through one transistor (the reference transistor) is mirrored by the other transistor(s) (the output transistor(s)).<br>
A MOSFET current mirror works similarly to a BJT current mirror. However, instead of the base-emitter voltage, the MOSFET current mirror relies on the gate-source voltage (Vgs) to establish the current. The gate-source voltage of both MOSFETs in the mirror is set equal, and by matching their dimensions and ensuring proper biasing, the output current in the mirrored transistor will be a copy of the reference current.<br>
## Types of Current Mirrors<br>
Simple Current Mirror: This is the basic current mirror configuration, where two transistors are used to mirror the current. It works well for moderate precision but suffers from issues like output impedance and variations due to mismatches in the transistors.<br>
Wilson Current Mirror: The Wilson current mirror is a more advanced version that improves output impedance and accuracy by adding additional transistors to provide better current mirroring performance.<br>
Cascode Current Mirror: The cascode current mirror uses an additional transistor to improve output resistance and make the current mirror less sensitive to changes in the load. This version has better performance in high-impedance environments.<br>
Improved Current Mirrors (e.g., Vbe-multiplier, etc.): These designs attempt to minimize the effects of transistor mismatch, temperature variations, and other real-world imperfections to provide more accurate and stable current mirrors.<br>
## applications of Current Mirrors<br>
Biasing: Current mirrors are frequently used to set bias currents in amplifier stages and other analog circuits, ensuring stable and predictable performance.<br>
Current Sources: They can act as precise current sources, which are useful in analog signal processing, active filters, and voltage-controlled current sources.<br>
Active Loads: Current mirrors are used in differential amplifier stages to provide a high output impedance, making them useful in increasing the gain of the amplifier.<br>
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
Our dc_offset = 0.838V and assume amplitude as 50mV and frequency as 1Khz.
The theriotical gain is-10V/V.But the obtained gain from the circuit is -10.2V/V.
![Screenshot (49)](https://github.com/user-attachments/assets/58ed09c2-e9a3-45db-ac96-7562aca26522)
## AC analysis<br>
Steps to get Ac analysis Waveform:
In simulation tab select AC Analysis.
In the AC Analysis tab, select Type of Sweep as Decade.
Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).
gain from the AC analysis(frequency response) is 22.36dB <br>
The obatined 3db B.W=2.267GHz.<br>
![Screenshot (49)](https://github.com/user-attachments/assets/585695f5-1821-4c40-a779-cf9f51206f38)
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
![Screenshot (51)](https://github.com/user-attachments/assets/0c1e3cf5-51ed-4048-8347-1fb4009268d6)
Our dc_offset = 0.763V and assume amplitude as 50mV and frequency as 1Khz.<br>
gain is -10V. obtained gain from thecircuit is -11.68V/V.<br>
### Ac analysis 
In simulation tab select AC Analysis.<br>
In the AC Analysis tab, select Type of Sweep as Decade.<br>
Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).<br>
![Screenshot (51)](https://github.com/user-attachments/assets/bcc72416-90cd-4d76-8e83-8ed839ec919e)
Expected gain in db of the circuit is 21.34db.But the obtained gain from the AC analysis(frequency response) is 24.6dB.<br>
### **Table:**
| **Parameter**  | **Mirror Ratio 1:1** (Theory) | **Mirror Ratio 1:1** (Practical) | **Mirror Ratio 1:2** (Theory) | **Mirror Ratio 1:2** (Practical) |
|---------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------|
| Av (in dB)    | 20 dB                        | 22.16 dB                     | 21.34 dB                     | 24.6 dB                     |
| Av (in V/V)   | 10                           | 10.2                          | 10                           | 11.68                         |
| 3 dB Bandwidth | -                            | 2.267 GHz                     | -                            | 1.173 GHz                     |  


 















