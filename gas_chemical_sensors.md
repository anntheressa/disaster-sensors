# Gas & Chemical Hazard Sensors  

Gas leaks and chemical releases can cause catastrophic industrial accidents. Sensors in this category detect toxic gases, flammable vapors, and harmful chemicals in the environment. They are widely used in industrial facilities, mines, chemical plants, emergency response systems, and smart-city safety networks.

---

# 1. Electrochemical Gas Sensors

### **Essential Facts**
- **Measures:** Toxic gases (CO, H₂S, NO₂, SO₂, Cl₂, O₃)  
- **Output:** Low-level current (nA–µA range) proportional to gas concentration  
- **Sampling rate:** 0.1–5 Hz  
- **Advantages:** High sensitivity, selective, low power  
- **Challenges:** Limited lifespan, cross-sensitivity, requires calibration  
- **Disaster use-cases:** Industrial leaks, indoor CO poisoning prevention, hazardous gas monitoring  

### **How Do They Work**
Electrochemical gas sensors contain electrodes and an electrolyte.  
When the target gas diffuses into the sensor, it undergoes a chemical reaction that produces an electrical current.  
The magnitude of the current is proportional to gas concentration.

These sensors are extremely sensitive and operate with near-zero power because the reaction itself produces the signal.

### **Why They Matter in Disasters**
- Detect toxic gas leaks before they reach dangerous levels  
- Allow early evacuation in industrial accidents  
- Provide real-time monitoring for first responders  

### **VLSI & Embedded Relevance**
- Requires ultra-low-current measurement circuits (transimpedance amplifiers)  
- ADC must have good resolution (16–24 bits often used)  
- Temperature/humidity compensation algorithms necessary  
- Low-power periodic sampling extends battery life  

---

# 2. Semiconductor Gas Sensors (MQ Series)

### **Essential Facts**
- **Measures:** Combustible gases (LPG, methane), ethanol, smoke, CO  
- **Sensor type:** Metal-oxide semiconductor (MOS)  
- **Output:** Resistance changes with gas concentration  
- **Advantages:** Very low cost, beginner-friendly  
- **Challenges:** High power consumption, poor selectivity, drift over time  
- **Disaster use-cases:** Gas leak detection (LPG, methane), smoke detection  

### **How Do They Work **
MQ sensors use a heated tin dioxide (SnO₂) surface.  
In clean air, oxygen adsorbs on the surface, capturing electrons and increasing resistance.  
When reducing gases (like LPG or CO) contact the surface:

- They react with the oxygen  
- Release electrons  
- Lower the sensor's resistance  

This resistance change is measured with a simple voltage divider.

### **Why They Matter in Disasters**
- Provide low-cost gas and smoke detection  
- Useful for large networks where sensor price must be minimal  
- Provide early warning of combustible gas leaks  

### **VLSI & Embedded Relevance**
- High heater power (100mW–900mW typical) is a major design challenge  
- ADC input must handle wide signal range  
- Duty cycling the heater reduces power but affects accuracy  
- Algorithms needed for drift compensation and calibration  

---

# 3. NDIR (Non-Dispersive Infrared) CO₂ Sensors

### **Essential Facts**
- **Measures:** CO₂ concentration via infrared absorption  
- **Sampling rate:** 0.1–1 Hz  
- **Advantages:** Good accuracy, selective, stable over time  
- **Challenges:** Higher cost, power consumption, warm-up time  
- **Disaster use-cases:** Indoor air quality, industrial CO₂ monitoring, confined-space safety  

### **How Do They Work **
CO₂ absorbs infrared light at specific wavelengths (around 4.26 µm).  
NDIR sensors:

1. Emit IR light  
2. Pass it through an optical chamber  
3. Measure attenuation at the CO₂ absorption band  

The decrease in intensity corresponds to gas concentration.

### **Why They Matter in Disasters**
- Detect CO₂ build-up in confined spaces (mines, sealed rooms)  
- Identify ventilation failures  
- Help prevent suffocation hazards  

### **VLSI & Embedded Relevance**
- Photodiode readout circuits require high stability  
- Low-power IR source control is critical  
- Filtering of noisy intensity measurements needed  
- Hardware-based signal averaging reduces MCU load  

---

# 4. VOC (Volatile Organic Compound) Sensors

### **Essential Facts**
- **Measures:** VOCs (e.g., benzene, formaldehyde, solvents)  
- **Sensor type:** MOS or photoionization detectors  
- **Advantages:** Detect broad classes of harmful chemicals  
- **Challenges:** Poor selectivity, humidity dependence  
- **Disaster use-cases:** Chemical spills, industrial plant monitoring, indoor air-quality hazards  

### **How Do They Work **

#### **MOS VOC sensors**
Similar to MQ sensors but optimized for VOC detection.  
Gas molecules reduce surface-bound oxygen, changing resistance.

#### **Photoionization detectors (PID)**
High-energy UV lamp ionizes VOC molecules.  
The resulting ions generate a current proportional to concentration.

### **Why They Matter in Disasters**
- Identify chemical spills or hazardous airborne compounds  
- Protect industrial workers and first responders  
- Provide rapid alerts for toxic atmospheric events  

### **VLSI & Embedded Relevance**
- PID sensors require stable high-voltage drivers  
- MOS sensors require heater power management  
- Filtering and threshold algorithms reduce false alarms  

---

# Summary

Gas and chemical sensors are essential for identifying life-threatening conditions during:

- Industrial gas leaks  
- Fires and smoke events  
- Chemical spills  
- Confined-space emergencies  

Each sensor type offers unique trade-offs:

| Sensor Type | Sensitivity | Power | Selectivity | Cost | Typical Use |
|-------------|-----------:|------:|------------:|-----:|--------------|
| Electrochemical | High | Very low | High | Moderate | Toxic gases |
| MOS (MQ) | Medium | High | Low | Very low | Combustible gas leaks |
| NDIR | High | Moderate | Very high | High | CO₂ monitoring |
| VOC (MOS/PID) | Medium | Varies | Medium | Moderate | Chemical hazards |

From a VLSI & embedded perspective:

- Analog front-ends and low-noise TIAs are critical  
- ADC bit depth affects detection accuracy  
- Power management heavily influences deployability  
- Calibration and drift compensation are major design challenges  

---

_To continue, proceed to the next sensor category in the notebook._
