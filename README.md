# Instrumentation-amplifier
## Aim : 
To design and analyse instrumentation amplifier using 741 IC Op-amp in LTSpice Simulator 
## Theory:
An instrumentation amplifier is a type of differential amplifier designed to amplify small signals while rejecting noise and interference, especially common-mode signals. It is extensively utilized in sensors, data acquisition systems, and medical devices where precise, low-level signal amplification is necessary. The amplifier is perfect for removing signals from noisy environments because it usually has a high input impedance, a low output impedance, and an excellent common-mode rejection ratio (CMRR). In order to enable simple gain adjustment with a single resistor, its architecture typically consists of three operational amplifiers: two for buffering the inputs and one for amplifying the difference between them.
## Design Question: 
Design an instrumentation amplifier using 3 op-amp configuration with the following constraints:
a) R1 = R2 = R3 = R4 = R5 = R6 = 100kΩ
b) Difference gain ADM = 20V/V
(Vcc = ±13.5V)
Find ACM (Common mode gain) & calculate CMRR for ADM = 20, and 50 V/V - use LT spice simulator.
## Calculation:
### For ADM =20v/V
ADM=[1+(2R5/RG)]
20-1=200000/RG
RG=200000/19
RG=10.5K ohm
### For ADM = 50V/V
RG=200000/49
RG=4.08K ohm
## Circuit Diagram with 10.5k ohm RG resistor and ADM=20V/V:
![10 5k without common mode voltage ckt](https://github.com/user-attachments/assets/5b1dfe26-8454-4617-adaf-bb08c67df4d2)
## Transient Analysis 
![10 5k without common mode voltage](https://github.com/user-attachments/assets/5d479557-131c-46e7-8e61-31c3ad03519d)
## circuit diagram with common mode voltage:
![10 5k with common mode voltage ckt](https://github.com/user-attachments/assets/b0304a65-c3cb-49dc-8681-805e81fbe18a)
## Transient analysis 
![10 5k with common mode volage](https://github.com/user-attachments/assets/68e71272-cc72-4faf-a41f-ac30498fe56e)
## Calculation of ACM and CMRR:
For ADM=20V/V
ACM= Vout/vin
   =0.9nv/0.1v
   =9n,
CMRR= 20log(ADM/ACM)
    = 20log(20/9n)
    =186.93dB
## Circuit Diagram With 4.08k ohm RG resistor and ADN=50V/V
![4 08 without common mode voltage ckt](https://github.com/user-attachments/assets/928ecad0-3071-4636-a18e-5a9bbdf27934)
## Transient Analysis 
![4 08k without common mode voltage](https://github.com/user-attachments/assets/6124be6d-2d1b-479e-b60f-4a8255cf49cf)
## Circuit Diagram with Common mode Voltage:
![4 08k with common mode voltage ckt](https://github.com/user-attachments/assets/76d7a075-3c03-4b38-960b-6d73224d5366)
## Transient Analysis
![4 08k with common mode voltage](https://github.com/user-attachments/assets/669e501a-7ae2-4cd2-ab5c-f7e56a5f4686)
## Calculation of ACM and CMRR:
### For ADM=50V/V
ACM= Vout/vin
=0.9nv/0.1v
=9n,
CMRR= 20log(ADM/ACM)
= 20log(50/9n)
=194.8dB,
## Procedure
1. Open LTspice
2. Create a New Schematic
3. Place Components: 3 Op-Amps (U1, U2, U3): Use opamp2 or UniversalOpamp2 (or a specific op-amp model like LT1001). 6 Resistors (R1–R6): R1, R2, R3, R4, R5, R6 = 100kΩ,RG = 4.08kΩ and RG=10.5kΩ
   1 Sine Wave Voltage Source (V3):
   Use a voltage source and set it to: SINE(0 0.1 1k) under Advanced settings (right-click the source > Advanced).
   2 DC Voltage Sources (V1, V2) for ±13.5V rails.
   Ground (Press G to place ground symbol).
4. Wire the Circuit
   U1 and U3 are input buffers.
   U2 is the differential amplifier stage.
   RG connects the two non-inverting amplifier outputs (U1, U3).
   The feedback from U2 goes to its inverting terminal.
   Make sure all resistor and op-amp nodes match the schematic layout.
5. Set Op-Amp Power Supplies
   For each op-amp, connect V+ to VDD (13.5V) and V− to VCC (−13.5V).
6. Label Nodes
7. Set Simulation Command
    Press S or go to Simulate = Edit Simulation Cmd.
    Use a Transient Analysis:
   .tran 0 0.5m 0
    Click "OK" and place the command on the schematic
8. Run Simulation
   Click the Run icon.
    Use the probe tool to click on nodes like VOUT and observe the output waveform.
9. follow the same procedure of Common mode voltage
# Result: 
Designed and Analysed the Instrumentation Amplifier using 741IC In LTSpice
## For ADM=20V/V
* ACM=9n,
* CMRR=186.93dB
## For ADM=50V/V
* ACM=9n,
* CMRR=194.8dB
# Inference:
1. This circuit rejects common-mode noise while properly amplifying tiny differential signals.
2. It offers high input impedance, accurate gain, and superior common-mode rejection as a real instrumentation amplifier.
3. Perfect for uses such as conditioning sensor signals (e.g., strain gauges, ECG).
4. Its design is adaptable because it only requires a single resistor (RG) to be changed to change the gain.
