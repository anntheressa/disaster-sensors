# Fire, Smoke & Heat Detection Sensors  


Rapid detection of fire and smoke is critical for preventing large-scale damage, enabling early evacuation, and supporting wildfire monitoring networks. Sensors in this category detect temperature changes, flame radiation signatures, and airborne particles produced by combustion.

---

# 1. Temperature Sensors (Thermistors & Thermocouples)

### **Essential Facts**
- **Measures:** Ambient or surface temperature  
- **Sensor types:** Thermistors (NTC/PTC), thermocouples  
- **Sampling rate:** 1–10 Hz  
- **Advantages:** Low-cost, low-power, highly responsive  
- **Challenges:** Noise, slow drift, susceptibility to localized heating  
- **Disaster use-cases:** Indoor fire alarms, wildfire boundary detection, HVAC smoke systems  

### **How Do They Work **

#### **Thermistors (NTC/PTC)**
A thermistor is a resistor whose resistance changes with temperature.  
- **NTC (Negative Temperature Coefficient):** Resistance decreases as temperature rises  
- **PTC:** Resistance increases as temperature rises  

They are paired with a simple voltage divider and read using an ADC.

#### **Thermocouples**
Two dissimilar metals form a junction. Temperature differences generate a small voltage (Seebeck effect).  
Used in environments requiring high temperature ranges.

### **Why They Matter in Disasters**
- Detect rapid temperature spikes that indicate fire ignition  
- Deployable in large sensor networks for wildfire perimeter monitoring  
- Complement IR/flame sensors for more reliable fire recognition  

### **VLSI & Embedded Relevance**
- Requires stable ADC reference and filtering  
- Linearization often needed for thermistor voltage curves  
- Thermocouples require high-gain, low-noise analog front-end  

---

# 2. Infrared (IR) Flame Sensors

### **Essential Facts**
- **Measures:** Infrared radiation signature of flames  
- **Typical spectrum:** 4.3 µm for hydrocarbon flames (CO₂ emission band)  
- **Sampling rate:** 10–50 Hz  
- **Advantages:** Fast response, works at long distances  
- **Challenges:** False alarms from sunlight or reflections  
- **Disaster use-cases:** Wildfire detection, industrial fire monitoring, gas fire surveillance  

### **How Do They Work **
Flames emit strong IR radiation at characteristic wavelengths, especially around 4.3 µm due to CO₂ emission.  
IR flame sensors contain:

- Optical filters (to isolate flame wavelengths)  
- Photodiodes or thermopile sensors  
- Signal conditioning to detect flicker patterns (typical 1–20 Hz oscillations)  

Flame flicker frequencies are an important distinguishing feature used to reduce false alarms.

### **Why They Matter in Disasters**
- Detect fires before visible smoke appears  
- Provide long-range sensing for forested or industrial areas  
- Trigger immediate alerts to reduce evacuation delays  

### **VLSI & Embedded Relevance**
- Flicker-detection algorithms (band-pass filtering)  
- Low-power IR photodiode readout circuits  
- Potential for on-chip infrared filtering or signal processing accelerators  

---

# 3. Smoke & Particulate Matter (PM2.5 / PM10) Sensors

### **Essential Facts**
- **Measures:** Smoke particles, dust, combustion aerosols  
- **Sensor types:** Optical scattering sensors (LED + photodiode), ionization detectors  
- **Sampling rate:** 1–10 Hz  
- **Advantages:** Highly sensitive to early smoke  
- **Challenges:** Contamination, humidity effects, false positives  
- **Disaster use-cases:** Indoor fire detection, wildfire smoke monitoring, air-quality alerts  

### **How Do They Work **

#### **Optical Scattering Sensors (most common)**
A small laser or IR LED illuminates an air chamber.  
Suspended particles scatter the light, which a photodiode detects.  
More particles → more scattering → larger signal.

Used in most modern air-quality sensors (e.g., PMS5003, SDS011).

#### **Ionization Smoke Detectors (older type)**
Use a tiny radioactive source to ionize air.  
Smoke disrupts ionized airflow, changing the current.  
Now being phased out but still common in homes.

### **Why They Matter in Disasters**
- Detect smoldering fires before open flames appear  
- Track wildfire smoke migration and air-quality hazards  
- Provide health risk assessments (PM2.5 is dangerous to lungs)  

### **VLSI & Embedded Relevance**
- Requires stable LED drivers and low-noise photodiode amplifiers  
- Signal proportional to scattering → needs calibration curves  
- Algorithms often compute averaged PM concentration over time  
- Duty cycling LED pulses can significantly reduce power consumption  

---

# Summary

Fire and smoke monitoring systems typically combine:

- **Temperature sensors** for rapid heat detection  
- **IR flame sensors** for real-time flame recognition  
- **PM sensors** for early smoke and air-quality warnings  

These sensors work together to create reliable early-warning systems for:

- Indoor fire alarms  
- Wildfire perimeter networks  
- Industrial safety monitoring  
- Public health air-quality systems  

From a VLSI and embedded systems perspective:

- Mixed-signal readout circuits are essential  
- Filtering and classification algorithms improve reliability  
- Power management strategies extend deployment lifetime  

---

_To continue, proceed to the next sensor category in the notebook._
