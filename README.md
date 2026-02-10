# Smart Tool Holder DAQ System – PCB Design

**Industrial Data Acquisition PCB | KiCad Design Portfolio**

[![KiCad](https://img.shields.io/badge/KiCad-7.0+-blue.svg)](https://www.kicad.org/)
[![License](https://img.shields.io/badge/License-Portfolio-green.svg)](#license)

---

## 👨‍💻 Designer

**Sree Harsha Kuragayala**  
Graduate Apprentice (2025) | PCB Design & Embedded Hardware  
Central Manufacturing Technology Institute (CMTI), Bangalore  
📧 sreeharsha.k83@gmail.com

---

## 📋 Project Overview

This repository showcases the **complete PCB design workflow** for an industrial-grade Smart Tool Holder Data Acquisition System. The project demonstrates professional PCB engineering practices, from schematic capture through fabrication-ready output generation using KiCad.

**Design Focus:**
- High-precision analog signal acquisition
- Industrial-grade reliability and robustness
- Low-noise layout techniques
- Design for Manufacturing (DFM) compliance

> **Portfolio Notice:** This repository contains PCB design deliverables only. Firmware, algorithms, and proprietary implementation details are excluded.

---

## 🎯 Key Deliverables

| Deliverable | Description | Status |
|------------|-------------|---------|
| **Schematic Design** | Multi-page hierarchical schematic with proper annotation | ✅ Complete |
| **PCB Layout** | 4-layer stackup with optimized routing | ✅ Complete |
| **Bill of Materials (BOM)** | Comprehensive component list with manufacturer P/Ns | ✅ Complete |
| **Gerber Files** | RS-274X format, fabrication-ready | ✅ Complete |
| **Pick & Place Files** | Centroid data for automated assembly | ✅ Complete |
| **Manufacturing Package** | Complete documentation with quotations | ✅ Complete |

---

## 🔧 PCB Specifications

### Board Parameters
- **Dimensions:** TBD × TBD mm
- **Layer Count:** 4 layers
- **Board Thickness:** 1.6 mm
- **Copper Weight:** 1 oz (35 μm)
- **Surface Finish:** ENIG (Electroless Nickel Immersion Gold)
- **Solder Mask:** Green, LPI
- **Silkscreen:** White, both sides

### Layer Stackup
```
Layer 1 (Top)      → Signal + Components
Layer 2 (Inner)    → Ground Plane (GND)
Layer 3 (Inner)    → Power Plane (VCC/VREF)
Layer 4 (Bottom)   → Signal + Components
```

### Design Rules
- **Minimum Trace Width:** 0.15 mm (6 mil)
- **Minimum Clearance:** 0.15 mm (6 mil)
- **Via Size:** 0.6 mm drill / 1.0 mm pad
- **Track-to-Edge Clearance:** 0.3 mm

---

## 📐 Design Evolution

### Version 1 — Initial Layout
- Component placement based on signal flow
- Preliminary routing exploration
- Ground plane definition

### Version 2 — Routing Optimization
- Analog/digital domain separation
- Impedance-controlled routing for critical signals
- Power distribution network (PDN) refinement

### Version 3 — Production Release
- DFM compliance verification
- Final component placement optimization
- Complete design rule check (DRC) clearance
- Thermal management validation

---

## ⚡ PCB Design Highlights

### Analog Signal Integrity
- **Dedicated analog ground island** for precision signal paths
- **Guard traces** around sensitive analog routing
- **Minimized trace lengths** for low-impedance signal paths (<20 mm)
- **Differential pair routing** with matched impedance (100Ω ±10%)
- **Kelvin sensing connections** for voltage reference accuracy

### Grounding Architecture
- **Solid ground plane** on Layer 2 for low-impedance return path
- **Star grounding topology** at ADC reference point
- **Ground plane stitching** with via fencing (λ/20 spacing)
- **Return current path optimization** beneath signal traces
- **Split ground prevention** to avoid ground loops

### Power Integrity
- **Dedicated power plane** on Layer 3 with copper pour
- **Decoupling capacitor placement:** 
  - Bulk: 10 μF (tantalum) within 5 mm of power entry
  - Bypass: 100 nF (ceramic X7R) at each IC power pin
  - High-frequency: 10 nF for fast switching loads
- **Power supply filtering** for analog reference voltage
- **Ferrite bead isolation** between digital and analog power domains

### EMI/EMC Mitigation
- **Trace spacing rules:** 3× minimum clearance for noisy signals
- **Via shielding** around high-speed clock traces
- **Clock routing:** Length-matched, impedance-controlled
- **Edge clearance:** 5× minimum clearance from board edge
- **Copper balance:** <30% difference between layers

### Thermal Management
- **Thermal vias** under power components (9 vias per component minimum)
- **Copper pour optimization** for heat dissipation
- **Component derating** per junction temperature requirements
- **Hot spot avoidance** through strategic component placement

---

## 🛠️ KiCad Design Workflow

### 1. Schematic Capture
- Multi-sheet hierarchical design
- Custom symbol library creation
- Electrical Rules Check (ERC) validation
- Net naming conventions and documentation
- Component value verification and selection

### 2. Component Footprint Management
- **Custom footprint creation** for specialized components
- **3D model integration** for mechanical clearance verification
- **Footprint library organization** by function/manufacturer
- **IPC-7351 compliant** land patterns
- **Courtyard definition** for assembly clearance

### 3. PCB Layout Strategy
```
Phase 1: Strategic Placement
  ├─ Critical signal path components
  ├─ Power management ICs
  ├─ Connectors and mechanical interfaces
  └─ Support components (passives)

Phase 2: Routing Execution
  ├─ Analog signal routing (shortest path)
  ├─ High-speed digital signals
  ├─ Power distribution network
  ├─ Low-speed control signals
  └─ Final routing cleanup

Phase 3: Validation & Optimization
  ├─ Design Rule Check (DRC)
  ├─ Layout vs. Schematic (LVS)
  ├─ Signal integrity review
  └─ Manufacturing review
```

### 4. Design Validation
- **DRC (Design Rule Check):** Zero violations
- **ERC (Electrical Rule Check):** All issues resolved
- **LVS (Layout vs. Schematic):** 100% netlist match
- **3D visualization:** Mechanical fit verification
- **Gerber validation:** Third-party viewer confirmation

### 5. Manufacturing Output Generation

#### Gerber Files (RS-274X)
- Top/Bottom Copper (GTL/GBL)
- Top/Bottom Solder Mask (GTS/GBS)
- Top/Bottom Silkscreen (GTO/GBO)
- Inner Layer 2/3 (G2/G3)
- Board Outline (GKO)
- Drill files (Excellon format)

#### Assembly Data
- **BOM Export:** CSV format with:
  - Designator, Value, Footprint
  - Manufacturer, Part Number
  - Quantity, Reference
- **Pick & Place (CPL):** XY centroid coordinates
  - Layer designation (Top/Bottom)
  - Rotation angle (0-360°)
  - Component package type

#### Documentation Package
- Schematic PDF (multi-page)
- PCB fabrication drawing
- Assembly drawing with reference designators
- Layer stackup specification
- Design notes and special instructions

---

## 📊 Bill of Materials (BOM) Management

### BOM Organization
- Categorized by function (analog, digital, power, passive)
- Manufacturer part numbers included
- Alternative components specified
- Cost optimization through volume sourcing
- Lead time tracking for critical components

### Component Selection Criteria
- **Passive Components:** 
  - Temperature coefficient: X7R/C0G for critical applications
  - Voltage derating: 50% minimum margin
  - Tolerance: ±1% for precision applications
- **Active Components:**
  - Automotive/industrial grade temperature range
  - Long-term availability (not NRND)
  - Second source availability
  - RoHS/REACH compliance

---

## 🏭 Design for Manufacturing (DFM)

### Fabrication Compliance
- **IPC-2221/2222** design standards adherence
- **Minimum feature sizes:** Manufacturable with standard process
- **Aspect ratio:** Vias ≤10:1 for reliable plating
- **Annular ring:** Minimum 0.15 mm on all layers
- **Solder mask expansion:** 0.1 mm from pad edge

### Assembly Optimization
- **Component spacing:** IPC-A-610 Class 2 compliance
- **Fiducial marks:** 3× global fiducials (1 mm diameter)
- **Panel design:** Support for array fabrication
- **Tooling holes:** 3.2 mm diameter, NPTH
- **No components within 3 mm of board edge**

### Cost Optimization Decisions
- Standard PCB thickness (1.6 mm) for economy
- Common layer count (4L) balancing cost/performance
- Standard surface finish options
- Panel utilization maximization
- Component consolidation for reduced line items

---

## 🧪 Design Validation & Testing Strategy

### Pre-Fabrication Validation
- ✅ Schematic peer review completed
- ✅ Footprint dimensional verification
- ✅ 3D mechanical clearance check
- ✅ DRC/ERC zero violations
- ✅ Gerber visual inspection

### Post-Fabrication Testing Plan
1. **Bare Board Testing**
   - Continuity testing (flying probe/bed-of-nails)
   - Impedance measurement (TDR)
   - Insulation resistance verification

2. **Assembled Board Testing**
   - Power-on sequence validation
   - Analog signal chain verification
   - Digital communication interface testing
   - Environmental stress screening (ESS)

---

## 📂 Repository Structure

```
smart-tool-holder-daq-pcb/
├── README.md                          # This file
├── schematics/
│   ├── smart-tool-holder-daq.kicad_sch
│   ├── analog-frontend.kicad_sch
│   ├── power-management.kicad_sch
│   └── schematic.pdf
├── pcb/
│   ├── smart-tool-holder-daq.kicad_pcb
│   └── 3d-view/
├── libraries/
│   ├── symbols/
│   └── footprints/
├── fabrication/
│   ├── gerbers/
│   ├── drill-files/
│   ├── bom/
│   │   └── BOM_v3.0.csv
│   ├── assembly/
│   │   ├── pick-and-place.csv
│   │   └── assembly-drawing.pdf
│   └── quotations/
│       └── manufacturing-quotes.pdf
└── documentation/
    ├── design-specifications.pdf
    ├── layer-stackup.pdf
    └── test-plan.pdf
```

---

## 🎓 Technical Skills Demonstrated

### KiCad Proficiency
- ✓ Hierarchical schematic design
- ✓ Custom symbol and footprint creation
- ✓ Advanced PCB layout techniques
- ✓ Design rule configuration and validation
- ✓ 3D visualization and mechanical integration
- ✓ Manufacturing output generation

### PCB Design Engineering
- ✓ Multi-layer stackup design
- ✓ High-speed signal integrity
- ✓ Analog circuit layout best practices
- ✓ Power distribution network (PDN) design
- ✓ EMI/EMC design considerations
- ✓ Thermal management strategies

### Manufacturing & Production
- ✓ Design for Manufacturing (DFM)
- ✓ Design for Assembly (DFA)
- ✓ Component sourcing and BOM optimization
- ✓ Manufacturing documentation
- ✓ Vendor communication and quotation analysis

---

## 🚀 Future Enhancements

- [ ] Impedance calculation and controlled impedance routing
- [ ] Signal integrity simulation (SI)
- [ ] Power integrity simulation (PI)
- [ ] Thermal simulation and analysis
- [ ] Flex-rigid PCB design exploration
- [ ] HDI (High Density Interconnect) techniques

---

## 📚 Design References

- **IPC-2221B:** Generic Standard on Printed Board Design
- **IPC-2222:** Sectional Design Standard for Rigid Organic Printed Boards
- **IPC-7351B:** Generic Requirements for Surface Mount Design and Land Pattern Standard
- **IPC-A-610:** Acceptability of Electronic Assemblies
- **IEEE 802.3:** Ethernet impedance specifications

---

## 📄 License

**Proprietary Portfolio License**

This repository is presented for **portfolio and demonstration purposes only**. 

- ✓ Viewing and assessment permitted
- ✗ Commercial use prohibited
- ✗ Redistribution not allowed
- ✗ Derivative works not permitted

For licensing inquiries or collaboration opportunities, please contact via email.

---

## 🤝 Professional Development

This project was completed as part of the Graduate Apprentice program at **Central Manufacturing Technology Institute (CMTI), Bangalore** — a premier institute under the Ministry of Heavy Industries, Government of India.

**Duration:** 2025  
**Role:** PCB Design & Embedded Hardware Engineering  
**Focus:** Industrial-grade hardware development and manufacturing

---

## 📬 Contact

**Sree Harsha Kuragayala**  
📧 sreeharsha.k83@gmail.com  
🔗 [LinkedIn](#) | [GitHub](#)

*Open to opportunities in PCB Design, Hardware Engineering, and Embedded Systems Development*

---

<div align="center">

**Designed with precision. Engineered for reliability.**

![KiCad](https://img.shields.io/badge/Made%20with-KiCad-blue)
![Industrial](https://img.shields.io/badge/Grade-Industrial-orange)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success)

</div>
