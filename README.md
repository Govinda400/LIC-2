# LIC-2
### **Differential Pair Amplifier: Overview and Analysis**

#### **Introduction:**
The differential pair amplifier, also known as the long-tailed pair, is a commonly used pair and it finds its use in OPerstional amplifiers (Op-Amps) and differential signal processing due to its ability to amplify the difference between two input signals while rejecting common-mode noise.
![Screenshot 2025-03-05 150843](https://github.com/user-attachments/assets/832b8523-8f8d-4cbc-b828-95ab797aafb4)

#### **Key Features:**
- **Differential Gain:** The amplifier amplifies the difference between two input signals.
- **Common-Mode Rejection:** The circuit effectively rejects common-mode noise or unwanted signals present at both inputs.
- **High Input Impedance:** Particularly in MOSFET-based designs, the amplifier exhibits high input impedance, making it suitable for high-precision applications.

#### **Applications:**
- **Operationaal Amplifiers (Op-Amps):** Commonly used in the input stage of op-amps.
- **Differential Signal Processing:** Useful in communication circuits and data transmission.
- **Instrumentation Amplifiers:** Essential in situations requiring precise amplification with low noise.

### **Structure and Working Principle:**
The basic structure of a differential pair amplifier consists of two transistors with their sources connected together. A current source is placed at their common node, and the output is taken from the drains of the transistors. The amplifier works by receiving two input signals, amplifying the difference between them, and rejecting any common-mode signals (noise). The transistors operate in saturation, and the current through them is controlled by a constant current source.
### **Question obtaianed:**
![Screenshot 2025-03-07 085723](https://github.com/user-attachments/assets/7f291f20-7911-4400-936d-534db008fe80)
### **Calculations before the simulation:**
![Screenshot 2025-03-07 090046](https://github.com/user-attachments/assets/14f6396d-b53e-4103-a712-cb3c3b932a3b)

### **Design Analysis:**
The differential amplifier's performance is assessed using various analyses, including:
1. **DC Analysis:** Focuses on setting up the correct operating point for the transistors.
2. **Transient Analysis:** Involves applying time-varying signals to observe the amplifier’s response in real time.
3. **AC Analysis:** Small-signal analysis is done to calculate voltage gain, bandwidth, and common-mode rejection ratio (CMRR).

____

### **Circuit 1: Resistor-Loaded Differential Pair**
<img width="538" alt="image" src="https://github.com/user-attachments/assets/b60de4b9-7b52-4e65-ba3d-b997c61d2629" />


#### **DC Analysis:**
The first circuit uses resistors as load elements. The key objective of the DC analysis is to ensure that both transistors are operating in saturation. To achieve this, the width-to-length ratio (W/L) and drain resistor \( R_D \) are adjusted. In this case, the practical drain current and other parameters closely match the theoretical predictions.

![Screenshot 2025-02-28 124256](https://github.com/user-attachments/assets/14590eb0-76ec-439c-9779-65deb3fe0a91)

- **DC Operating Points:**
  - **Theoretical Output Voltage (V_outcm):** 1.25V
  - **Practical Output Voltage:** 1.250V
  - **Drain Current (Id1, Id2):** 0.5mA (Theoretical), 4.9mA (Practical)
  - **Gate-Source Voltage (Vgs):** 0.8V (Practical)

The current through both transistors is split evenly, and the drain-to-source voltage (\( V_{ds} \)) is checked to ensure that both transistors remain in saturation.

#### **Transient Analysis:**
For transient analysis, a time-varying differential input signal is applied. This analysis helps observe how the circuit responds to dynamic inputs and ensures the proper amplification of the differential signal, while effectively rejecting common-mode signals.

- **Key Results:**
  - **Amplitude of Input:** 50mV
  - **Voltage Gain (Av):** 1.44V/V
  - **Common-Mode Input Voltage (V_{in}cm):** 1.2V
  - The amplifier successfully rejects common-mode noise and amplifies the differential signal.
<img width="958" alt="image" src="https://github.com/user-attachments/assets/18e0128b-ee37-4eec-b25f-063c1aa49499" />

#### **AC Analysis:**
In AC analysis, a small-signal approach is used to calculate the voltage gain and other parameters like the common-mode rejection ratio (CMRR). The voltage gain is calculated using \( A_v = g_m \cdot R_D \), where \( g_m \) is the transconductance of the transistor.
![image](https://github.com/user-attachments/assets/c587bc6a-3bf9-4930-8f8c-1fdb2c2f8ce4)
<img width="578" alt="image" src="https://github.com/user-attachments/assets/dffb5ab7-f4e4-43d6-9a7e-4477471f5afa" />

- **Theoretical Gain (Av):** 4.31V/V
- **Practical Gain:** 4V/V
- **Gain in dB (Theoretical):** 11.59 dB
- **Gain in dB (Practical):** 11.76 dB

The results show that the resistor-loaded differential pair performs well with a reasonable voltage gain and common-mode rejection.

---

### **Circuit 2: Current Source-Loaded Differential Pair**

<img width="366" alt="image" src="https://github.com/user-attachments/assets/51f5c551-54e9-4e34-ab56-276d706773aa" />

#### **DC Analysis:**
The second circuit replaces the resistors with a current source at the tail. The current source provides a constant current, improving the amplifier's stability and performance. The analysis ensures the transistor's operation in saturation.
<img width="215" alt="image" src="https://github.com/user-attachments/assets/3265b07d-5cf2-4b4c-b065-05fb4c75717f" />

- **Key Parameters:**
  - **V_{gs} > V_{th}** (Threshold Voltage)
  - **V_{ds} > V_{ov}** (Overdrive Voltage)
  - The current source guarantees that the transistors operate in their saturation region, leading to better stability and gain.

#### **Transient Analysis:**
For transient analysis, a 50mV amplitude signal is applied, and the voltage gain is observed.
<img width="581" alt="image" src="https://github.com/user-attachments/assets/9255cb5f-9365-458d-8f2f-3006152f8179" />

- **Key Results:**
  - **V_{in}cm(min):** 0.8V
  - **V_{in}cm(max):** 1.65V
  - **Voltage Gain:** The gain achieved is similar to the previous circuit, demonstrating the consistent performance of the amplifier.

#### **AC Analysis:**
The voltage gain is computed in the same way as the resistor-loaded pair. The result shows a similar voltage gain in both the theoretical and practical scenarios.
![image](https://github.com/user-attachments/assets/9e66cfc1-0a17-40e5-a1ae-5a98cdf1f69a)

- **Theoretical Gain (Av):** -4.31V/V
- **Practical Gain:** -4V/V
- **Gain in dB (Theoretical):** 11.59 dB
- **Gain in dB (Practical):** 11.78 dB

The current-source-loaded differential pair offers good performance, with improved stability compared to the resistor-loaded design.

---

### **Circuit 3: Simple Current Source Differential Pair**

#### **DC Analysis:**
The third circuit is a simplified version of the current-source-loaded differential pair, where the current source is used in the tail of the differential pair. The analysis ensures that the transistors stay in saturation under all operating conditions.
<img width="578" alt="image" src="https://github.com/user-attachments/assets/109a2ca8-4a82-4295-853c-663a4906c2c9" />

#### **Transient Analysis:**
Similar to the previous circuits, a 50mV differential signal is applied, and the amplifier’s transient response is observed.
<img width="579" alt="image" src="https://github.com/user-attachments/assets/2173eded-3a07-4bc2-80e8-1d83954caa5c" />

- **Results:**
  - **V_{in}cm(min):** 0.8V
  - **V_{in}cm(max):** 1.65V
  - The amplifier operates correctly, with the output amplifying the differential signal and rejecting common-mode signals.

#### **AC Analysis:**
As with the previous circuits, the small-signal analysis is carried out to determine the voltage gain and other relevant parameters.
<img width="579" alt="image" src="https://github.com/user-attachments/assets/54ee7995-3e73-435e-81a5-39b31b7db114" />

- **Theoretical Gain (Av):** 4.31V/V
- **Practical Gain:** 4V/V
- **Gain in dB (Theoretical):** 11.59 dB
- **Gain in dB (Practical):** 11.78 dB

The performance is consistent with the other two circuits, with a reasonable voltage gain and effective common-mode rejection.

---

### **Conclusion:**
All three circuits—the resistor-loaded, current-source-loaded, and simple current-source differential pairs—demonstrate the ability to amplify differential signals while rejecting common-mode noise. The use of a constant current source instead of resistors improves stability, gain, and overall performance, particularly in the current-source-loaded and simple current-source circuits.

**Inference:**
1. **Tail Resistor vs. Current Source:** Replacing the tail resistor with a current source improves amplifier stability and gain.
2. **Gain Consistency:** All three circuits show similar voltage gain, with minor variations due to practical implementation.
3. **Common-Mode Rejection:** The circuits successfully reject common-mode signals, confirming their suitability for differential signal applications.
4. **Transistor Saturation:** Ensuring that both transistors remain in saturation is essential for proper operation, and input voltages must be within an appropriate range.

In summary, the differential amplifier is a robust and essential circuit in analog electronics, with the current-source-loaded designs providing superior performance over resistor-loaded designs.

