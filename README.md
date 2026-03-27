Overview:

Designed a compact power management PCB to support a portable environmental sensing platform deployed in remote outdoor conditions. The system is powered by 4×AA batteries, where supply voltage can vary significantly depending on battery chemistry, load, and discharge state.
To ensure reliable operation, the design integrates a buck-boost converter for voltage regulation and an ideal diode controller to enable seamless power switching and prevent reverse current flow. This allows the system to maintain a stable output rail while supporting scenarios such as battery replacement or auxiliary power input without interruption.

Key Features: 
- Wide-input buck-boost regulation (TPS63070) for consistent output across battery discharge range
- Ideal diode stage (LM66200) for efficient power OR-ing and reverse current protection
- Designed for 4×AA battery operation (~3V–6V input range)
- Adjustable regulated output suitable for embedded systems and sensors
- Parallel input/output capacitors for improved transient response
- Integrated enable, power-good, and sync control signals
- On-board power indicator LED for system status
- Custom 2-layer PCB (KiCad) with dedicated ground plane
- Stitching vias and ground plane design to reduce noise and improve stability

Design Highlight: 

One design decision I focused on was separating power regulation and power path control instead of relying on a single integrated solution.

By combining a buck-boost converter with an ideal diode controller, the system:
- Maintains a stable output voltage regardless of battery condition
- Prevents backfeeding into the input source, protecting batteries and external supplies
- Enables hot-swapping or dual-input scenarios without disrupting operation

This architecture is especially useful in field-deployed systems where power conditions are unpredictable and reliability is critical.

Hardware Design: 

Designed full schematic and PCB layout in KiCad
Structured layout into functional blocks:
- Input filtering and bulk capacitance
- Switching regulator stage
- Feedback and control network
- Ideal diode output stage
- Used multiple capacitors in parallel to reduce ESR and improve load response
- Routed high-current paths (VIN, VOUT, GND) with short, wide traces
- Implemented a solid B.Cu ground plane with stitching vias for low impedance return paths
- Placed decoupling capacitors close to IC pins to minimize switching noise
- Kept control signals (EN, PS, PG) isolated from switching nodes

Images:
![Buck](https://github.com/user-attachments/assets/d8782bf6-5d06-4de3-b4f3-fd31c03d19cc)




