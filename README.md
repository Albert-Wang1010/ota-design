# Two-Stage Miller-Compensated OTA in 0.25µm CMOS - Supplementary Materials

Supplementary materials for the two-stage Miller-compensated operational transconductance amplifier design project. Contains complete simulation figures and test waveforms supporting the main technical paper.

**For complete technical documentation, methodology, and analysis, see [docs/Analog_Final_Proj.pdf](docs/Analog_Final_Proj.pdf)**

---

## Project Overview

**Title:** *Two-Stage Miller-Compensated Operational Transconductance Amplifier: Design, Optimization, and Characterization in 0.25µm CMOS*

**Key Results:**
- Open-loop gain: 76.12 dB
- Phase margin: 47.19° (stable operation)
- Closed-loop bandwidth: 203.17 kHz @ 4 V/V gain
- Power consumption: 691.7 µA from ±1.25V supplies
- Unity-gain frequency: 359 kHz
- Figure of merit: 258 MHz·pF/mA

**Architecture:**
- Two-stage topology with Miller compensation
- Differential NMOS input pair (M1-M2) with PMOS active load (M3-M4)
- Common-source output stage (M5-M6) driving 880 pF load
- Current mirror bias network with 26%/72% stage allocation
- Nulling resistor (Rc = 740Ω) for RHP zero cancellation
- Compensation capacitor (Cc = 330 pF)

---

## Repository Contents

This repository provides **complete simulation figures and supplementary materials** that extend beyond what's included in the main paper. All figures are organized by analysis type for easy reference.

### Structure
```
ota-design/
├── docs/
│   └── Analog_Final_Proj.pdf        # Complete technical paper (primary documentation)
│
└── figures/
    ├── architecture/
    │   ├── schematic.png                    # Complete OTA schematic
    │   └── schematic_cadence.png            # Cadence schematic capture
    │
    ├── dc_analysis/
    │   ├── dc_accuracy_vs_input.png         # 1% accuracy range
    │   ├── dc_offset_measurement.png        # Offset characterization
    │   ├── dc_transfer_curve.png            # Open/closed-loop transfer
    │   └── small_signal_parameters.png      # Extracted parameters
    │
    ├── ac_analysis/
    │   ├── closedloop_gain.png              # Closed-loop gain (linear)
    │   ├── open_loop_bode.png               # Open-loop Bode (dB)
    │   └── closedloop_bode.png              # Closed-loop Bode (dB)
    │
    ├── transient/
    │   ├── pulse_train_response.png         # 200 kHz square wave
    │   ├── step_response_1mv_pos.png        # +1 mV step
    │   ├── step_response_1mv_neg.png        # -1 mV step
    │   ├── step_response_100mv_pos.png      # +100 mV step
    │   ├── step_response_100mv_neg.png      # -100 mV step
    │   ├── step_response_269mv_pos.png      # +269 mV step (max)
    │   └── step_response_316mv_neg.png      # -316 mV step (min)
    │
    └── pvt_analysis/
        ├── dc_offset_0C.png                 # 0°C offset characterization
        ├── dc_offset_09vdd.png              # 0.9× supply offset
        ├── dc_offset_11vdd.png              # 1.1× supply offset
        ├── dc_offset_80C.png                # 80°C offset characterization
        ├── temp_0C_bode.png                 # 0°C frequency response
        ├── temp_80C_bode.png                # 80°C frequency response
        ├── temp_0C_transient.png            # 0°C step response
        ├── temp_80C_transient.png           # 80°C step response
        ├── voltage_09vdd_input_offset.png   # 0.9× supply input range
        └── voltage_11vdd_input_offset.png   # 1.1× supply input range
```

### What's Included

Each analysis directory contains:
- **Simulation Waveforms** - Cadence Spectre screenshots
- **Extracted Data** - Performance metrics and measurements
- **Design Characterization** - Complete DC, AC, transient, and PVT analysis

**Materials provided:**
- Complete schematic (paper figure and Cadence capture)
- DC transfer characteristics and offset measurements
- AC frequency response (open-loop and closed-loop)
- Transient step responses across signal amplitudes
- PVT corner analysis (voltage ±10%, temperature 0-80°C)

---

## Quick Links

- **Main Paper:** [docs/Analog_Final_Proj.pdf](docs/Analog_Final_Proj.pdf)
- **Complete Schematic:** [figures/architecture/schematic.png](figures/architecture/schematic.png)
- **DC Analysis:** [figures/dc_analysis/](figures/dc_analysis/)
- **AC Frequency Response:** [figures/ac_analysis/](figures/ac_analysis/)
- **Transient Response:** [figures/transient/](figures/transient/)
- **PVT Corner Analysis:** [figures/pvt_analysis/](figures/pvt_analysis/)

---

## Design Specifications

| Parameter | Specification | Achieved |
|-----------|--------------|----------|
| Technology | 0.25µm CMOS | - |
| Supply Voltage | ±1.25V | ±1.25V |
| Closed-Loop Gain | 4 V/V | 3.998 V/V (0.05% error) |
| Maximum Current | <700 µA | 691.7 µA |
| Load Capacitance | 880 pF | 880 pF |
| Open-Loop Gain | - | 76.12 dB |
| Phase Margin | >45° | 47.19° |
| Bandwidth (-3dB) | Maximize | 203.17 kHz |
| DC Accuracy | <0.1% | <0.1% (±1 mV range) |
| Unity-Gain Freq | - | 359 kHz |

---

## Design Methodology

**Technology:** 0.25µm CMOS (TSMC tsmc025.scs)  
**Tools:** Cadence Virtuoso (schematic/simulation), Cadence Spectre (SPICE), Cadence Calculator (measurements)  

**Approach:** Systematic design flow incorporating pre-sizing analysis, small-signal parameter extraction, iterative optimization, and comprehensive PVT corner verification.

For detailed transistor sizing rationale, pole-zero analysis, stability calculations, current allocation strategy, and complete design methodology, refer to the main paper.

---

## Academic Context

Completed as part of Columbia University's **Analog Electronic Circuits (EE4312)** course, Fall 2025. Demonstrates systematic analog amplifier design methodology from specification through PVT-validated implementation.

**Author:** Albert Wang  
**Institution:** Columbia University, Department of Electrical Engineering  
**Contact:** aw3741@columbia.edu

---

## Acknowledgments

The author thanks Richard Oh for contributions to the final transistor sizing refinement and assistance with hand calculations during the initial design phase.

---

*For questions about the design methodology, technical details, or collaboration opportunities, please refer to the paper first, then contact via email.*