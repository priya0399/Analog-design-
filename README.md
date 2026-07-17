# Analog Circuits Design - Amplifier Collection

A focused repository for MOSFET amplifier circuit designs and analyses in **130nm technology**. This collection includes comprehensive documentation, simulations, and practical implementations of fundamental and advanced amplifier topologies using ElectricBinary and LTspice.

## 📋 Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Amplifier Topologies](#amplifier-topologies)
- [Technology & Tools](#technology--tools)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Circuit Details](#circuit-details)
- [Simulations](#simulations)
- [Performance Metrics](#performance-metrics)
- [Analysis Types](#analysis-types)
- [Contributing](#contributing)
- [Resources](#resources)
- [License](#license)
- [Contact](#contact)

## 🎯 Overview

This repository contains detailed designs and analyses of **130nm CMOS** MOSFET amplifier circuits, focusing on practical implementations and theoretical understanding. Each amplifier topology includes:

- **Schematic diagrams** with component specifications (designed in ElectricBinary)
- **SPICE simulations** verified with 130nm technology files (LTspice netlists)
- **Hand calculations** and design equations for 130nm process
- **Complete analysis suite**: DC operating point, transient response, and AC frequency response
- **Performance characterization** (gain, bandwidth, input/output impedance)
- **Layout considerations** for 130nm PDK implementation
- **Frequency response plots** and comprehensive AC/DC analysis

## 📁 Repository Structure

```
Analog-design-/
├── README.md
├── technology/
│   └── 130nm-techfile.lib (130nm MOSFET models)
├── amplifiers/
│   ├── 01-Common-Source-Amp/
│   │   ├── schematic.png (ElectricBinary)
│   │   ├── design-guide.md
│   │   ├── bom.csv
│   │   ├── simulation.cir (LTspice netlist)
│   │   ├── analysis/
│   │   │   ├── dc-analysis.txt
│   │   │   ├── transient-analysis.txt
│   │   │   ├── ac-analysis.txt
│   │   │   ├── dc-sweep-results.csv
│   │   │   ├── transient-waveforms.csv
│   │   │   └── bode-plots.csv
│   │   └── analysis.md
│   ├── 02-Common-Drain-Amp/
│   │   ├── schematic.png (ElectricBinary)
│   │   ├── design-guide.md
│   │   ├── bom.csv
│   │   ├── simulation.cir (LTspice netlist)
│   │   ├── analysis/
│   │   │   ├── dc-analysis.txt
│   │   │   ├── transient-analysis.txt
│   │   │   ├── ac-analysis.txt
│   │   │   └── results.csv
│   │   └── analysis.md
│   ├── 03-Common-Gate-Amp/
│   ├── 04-Cascode-Amp/
│   ├── 05-Differential-Amp/
│   └── 06-Current-Mirror-with-CS-Amp-Load/
├── documentation/
│   ├── 130nm-design-guide.md
│   ├── design-equations.md
│   ├── mosfet-parameters-130nm.md
│   ├── measurement-guide.md
│   └── simulation-procedures.md
├── simulations/
│   ├── spice-models/
│   │   └── 130nm-mosfet.lib
│   └── templates/
│       └── amplifier-template.cir
└── resources/
    ├── references/
    │   └── 130nm-pdk-documentation.pdf
    └── datasheets/
```

## 🔌 Amplifier Topologies (130nm CMOS)

This repository covers six essential MOSFET amplifier configurations optimized for 130nm technology:

### 1. **Common Source Amplifier (CS)**
- Single-stage voltage amplifier
- High voltage gain in 130nm process
- High input impedance
- **Analysis**: DC biasing, transient settling, AC frequency response up to GHz range
- Applications: preamps, voltage amplification, first gain stage

### 2. **Common Drain Amplifier (CD) / Source Follower**
- Unity-gain buffer amplifier
- Very low output impedance
- High input impedance
- **Analysis**: DC operating points, transient response to step input, AC bandwidth
- Applications: impedance buffering, driver stages, output buffers

### 3. **Common Gate Amplifier (CG)**
- Low input impedance
- High output impedance
- Improved high-frequency performance
- **Analysis**: DC sweep, transient dynamics, AC response with CG configuration
- Applications: RF input stages, transimpedance amplifiers

### 4. **Cascode Amplifier**
- Common Source + Common Gate cascade
- Very high voltage gain (~60-80 dB achievable in 130nm)
- Extended bandwidth with Miller effect cancellation
- **Analysis**: Complete AC/DC/transient characterization
- Applications: operational amplifiers, high-gain stages, precision circuits

### 5. **Differential Amplifier**
- Differential to single-ended conversion
- High CMRR in 130nm matched pairs
- Large linear input range
- **Analysis**: DC transfer curve, differential transient response, AC CMRR measurement
- Applications: op-amp input stages, comparators, precision measurements

### 6. **Current Mirror with Common Source Amplifier Load**
- Active load topology using current mirror
- Maximum voltage gain in 130nm process
- Improved linearity vs passive loads
- **Analysis**: DC gain, transient linearity, AC frequency response
- Applications: operational amplifier stages, precision multipliers, analog filters

## 🔧 Technology & Tools

### Technology Node: **130nm CMOS**

| Specification | Value |
|---------------|-------|
| **Minimum Gate Length** | 0.13 µm |
| **Metal Layers** | 6 |
| **Typical Operating Voltage** | 1.2-1.8V |
| **Max Frequency** | ~1-2 GHz |
| **Leakage Current** | Low (moderate for 130nm) |
| **Process Corners** | SS, TT, FF, SF, FS |

### Design Tools Used

| Tool | Purpose | Version | File Format |
|------|---------|---------|------------|
| **LTspice** | Circuit simulation & analysis | XVII or later | `.cir`, `.asc` |
| **ElectricBinary** | Schematic capture | Latest | `.png` exports |
| **130nm PDK** | Process technology file | Version X | `.lib`, `.mod` |
| **Python** | Data analysis & plotting | 3.8+ | `.csv` → plots |

### EDA Tools for Full Flow

| Tool | Purpose | Usage |
|------|---------|-------|
| **LTspice** | SPICE simulation | DC/AC/Transient analysis |
| **ElectricBinary** | Schematic design | Circuit entry & visualization |
| **Cadence Virtuoso** | Full layout design | Layout & parasitic extraction |
| **Synopsys HSPICE** | Advanced simulation | Monte Carlo, corner analysis |
| **Python (matplotlib)** | Results visualization | Bode plots, gain curves |

## 🚀 Getting Started

### Prerequisites

- Understanding of CMOS technology and 130nm process specifics
- Familiarity with circuit analysis (hand calculations)
- Knowledge of DC, AC, and transient analysis concepts
- **LTspice** installed for simulation
- **ElectricBinary** or image viewer for schematics
- 130nm technology file (included in repository)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/priya0399/Analog-design-.git
   cd Analog-design-
   ```

2. **Install LTspice** (required):
   ```
   Download: https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html
   Version: LTspice XVII or later
   Platform: Windows, Mac, Linux
   ```

3. **Verify 130nm technology file:**
   ```bash
   ls technology/130nm-techfile.lib
   ```

4. **Navigate to an amplifier:**
   ```bash
   cd amplifiers/01-Common-Source-Amp/
   cat simulation.cir  # View the netlist with 130nm models
   ```

## 📚 Circuit Details

### Each amplifier folder includes:

| File | Description | Content |
|------|-------------|---------|
| **schematic.png** | Circuit diagram from ElectricBinary | Component connections, device sizes (W/L) |
| **design-guide.md** | Theory and design procedure | Equations, calculations, hand analysis |
| **bom.csv** | Component list | Part numbers, values, quantities |
| **simulation.cir** | LTspice netlist with 130nm models | Ready-to-simulate spice deck |
| **analysis.md** | Results and verification | Measured gains, impedances, frequencies |
| **dc-analysis.txt** | DC operating point results | Quiescent voltages, currents, power |
| **transient-analysis.txt** | Time-domain results | Step response, settling time, overshoot |
| **ac-analysis.txt** | Frequency response results | Gain, phase, -3dB bandwidth, poles/zeros |

### Design Parameters for 130nm:

```
Technology Node:  130nm
Oxide Thickness:  ~3nm
Supply Voltage:   1.8V (nominal), 1.62-1.98V (range)
Temperature:      27°C (nominal), -40 to 125°C operating range
Process Corners:  SS, TT, FF, SF, FS (for robustness verification)

Typical Device Parameters:
  nMOS Vt:        ~0.35-0.45V
  pMOS Vt:        ~-0.35 to -0.45V
  Cox (nMOS):     ~7-8 fF/µm²
  µn (nMOS):      ~300-350 cm²/V·s
  VA (Early):     ~15-25V
```

## 🔬 Simulations - Complete Analysis Suite

### Analysis Types Performed on Each Circuit:

#### 1. **DC Operating Point Analysis (.op)**
```
Purpose: Find quiescent (bias) conditions
Measures: VGS, VDS, ID for each transistor
Verifies: MOSFET saturation, power consumption
LTspice Command: .op
```

#### 2. **Transient Analysis (.tran)**
```
Purpose: Time-domain response to input signals
Measures: Rise/fall times, settling behavior, signal integrity
Typical Sweep: 0 to 100ns with 10ps resolution
Simulates: Step input response, small-signal transient
LTspice Command: .tran 0 100n 0 10p
```

#### 3. **AC Frequency Response Analysis (.ac)**
```
Purpose: Frequency-dependent behavior (Bode plots)
Measures: Magnitude response, phase response, bandwidth
Frequency Range: 1Hz to 10GHz (decade sweep with 100 points/decade)
Calculates: -3dB bandwidth, phase margin, gain margin
LTspice Command: .ac dec 100 1 10G
```

### Running Simulations in LTspice:

**Method 1: GUI (Recommended for visualization)**
```
1. Open LTspice XVII
2. File → Open → select amplifier/simulation.cir
3. Simulate → Run (or Ctrl+R)
4. Click on nodes to plot voltages
5. Right-click on waveform → Export Data (CSV)
```

**Method 2: Batch mode (Automated testing)**
```bash
ltspice -b simulation.cir -o results.txt
```

**Method 3: With parameter sweeps**
```
.step param W_M1 10u 100u 10u    # Sweep transistor width
.dc V_in 0 5 0.01                # DC sweep input voltage
.measure dc gain FIND V(out)/V(in)
```

### Example LTspice Netlist for Common Source (130nm):

```spice
* 130nm Common Source Amplifier
.include technology/130nm-techfile.lib

* Power supply
Vdd 1 0 DC 1.8

* Input signal (transient: step + AC sine)
Vin in 0 DC 0.9 AC 0.01 PWL(0 0 1n 1 2u 1)

* MOSFET devices (W/L in microns)
M1 out in 0 0 nmos W=10u L=0.13u    * Input stage
M2 out vdd vdd vdd pmos W=20u L=0.13u * Load

* Biasing
Ibias vdd 1 100u

* Load resistor (optional)
Rload out 0 1Meg

* Capacitive load
Cload out 0 1p

* Analysis commands
.op                           * DC operating point
.tran 0 100n 0 10p           * Transient 0-100ns
.ac dec 100 1 1G             * AC 1Hz-1GHz

* Measurements
.measure ac gain FIND vdb(out) AT=100Meg
.measure ac bw FIND frequency WHEN vdb(out)=gain-3

.end
```

## 📊 Performance Metrics at 130nm

Each amplifier is characterized with these metrics:

| Parameter | Units | Typical 130nm | Measurement Method |
|-----------|-------|---------------|-------------------|
| **Voltage Gain (Av)** | dB, V/V | 20-80 dB | AC analysis magnitude |
| **Input Impedance (Zin)** | Ω | 10kΩ - TΩ | Calculated / AC sweep |
| **Output Impedance (Zout)** | Ω | 100Ω - 100kΩ | AC impedance measurement |
| **Bandwidth (-3dB)** | MHz/GHz | 10MHz - 1GHz | AC analysis frequency |
| **Slew Rate** | V/µs | 1-100 V/µs | Transient step response |
| **Settling Time** | ns | 1-100 ns | Transient 90% settling |
| **CMRR (Differential)** | dB | >60 dB | Common mode analysis |
| **Power Consumption** | mW | 0.1-10 mW | DC operating point |
| **Input Offset Voltage** | mV | <5 mV | Differential pair analysis |
| **PSRR** | dB | >50 dB | Supply variation AC |

## 📈 Analysis Types Detailed

### DC Analysis Results Include:

```
✓ Quiescent operating point (VGS, VDS, ID)
✓ Voltage at each node
✓ Current through each device
✓ Power dissipation per transistor
✓ Verification of saturation region
✓ Transconductance (gm) at operating point
```

### Transient Analysis Results Include:

```
✓ Voltage waveforms vs time
✓ Rise time / Fall time
✓ Settling time to steady state
✓ Overshoot / Undershoot
✓ Maximum slew rate
✓ Small-signal transient behavior
```

### AC Analysis Results Include:

```
✓ Bode magnitude plot (dB vs frequency)
✓ Bode phase plot (degrees vs frequency)
✓ -3dB bandwidth frequency
✓ Low-frequency gain (DC gain)
✓ Poles and zeros location
✓ Phase margin and gain margin
✓ Input/output impedance vs frequency
```

## 🤝 Contributing

To contribute improvements or additional analysis:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/130nm-optimization`
3. Add contributions:
   - Enhanced schematics (ElectricBinary)
   - Improved LTspice netlists with 130nm PDK
   - Corner analysis (SS, TT, FF, SF, FS)
   - Temperature sweep results
   - Monte Carlo statistical analysis
   - Layout with parasitic extraction
4. Include complete DC/AC/transient analysis results
5. Submit pull request

### Contribution Standards:

- High-quality schematics (ElectricBinary PNG export, 300 DPI)
- Verified LTspice simulations with 130nm models
- Complete analysis suite (DC, AC, transient)
- Documented equations and assumptions
- CSV exports of simulation results
- Process corner verification
- Temperature range testing

## 📚 Resources

### 130nm CMOS Technology Reference:

- **Technology Node Info**: 130nm TSMC, Samsung, IBM foundries
- **Standard Cell Libraries**: Available in PDK
- **Design Rules**: 8-metal, 6-poly layer stack
- **Design Margin**: 0.13µm minimum gate length

### Learning Materials:

**Textbooks:**
- *Design of Analog CMOS Integrated Circuits* - Razavi (best for 130nm design)
- *CMOS Analog Circuit Design* - Allen & Holberg
- *Microelectronic Circuits* - Sedra & Smith

**Application Notes:**
- Analog Devices: [Design Resources](https://www.analog.com/en/design-center/application-notes-and-tutorials.html)
- Texas Instruments: [Design Guides](https://www.ti.com/design-resources)
- PDK Documentation from foundry (TSMC, Samsung, IBM)

### LTspice Resources:

- Built-in LTspice Help & Tutorial
- [LTspice Documentation](https://www.analog.com/media/en/technical-documentation/user-guides/LTspiceUserGuide.pdf)
- SPICE Netlist Reference

### 130nm Process Files:

- Technology file: `technology/130nm-techfile.lib`
- MOSFET models: Level 49 (BSIM3v3) or Level 54 (BSIM4)
- Parasitics: Metal sheet resistance, via resistance

## 📄 License

This project is licensed under the [MIT License](LICENSE) - free to use for educational and research purposes.

## 💬 Contact & Support

- **Author**: [priya0399](https://github.com/priya0399)
- **Issues & Questions**: [GitHub Issues](https://github.com/priya0399/Analog-design-/issues)
- **Discussions**: [GitHub Discussions](https://github.com/priya0399/Analog-design-/discussions)

## ⚡ Quick Reference - 130nm Design

### Small-Signal Parameters (130nm typical):

```
gm = √(2 × µn × Cox × (W/L) × ID)
    where µn ≈ 320 cm²/V·s for 130nm nMOS
    Cox ≈ 7.5 fF/µm² for 130nm

ro = VA / ID
    where VA ≈ 20V (Early voltage, 130nm)

Gain (Common Source):
Av = -gm × ro = -√(2 × µn × Cox × (W/L) × ID) × (VA/ID)
```

### Typical 130nm Device Sizes:

```
High-speed circuits:     W/L = 1-5µm
Standard gain stages:    W/L = 10-50µm
Low-impedance buffers:   W/L = 100-500µm
Differential pairs:      W/L = 20-40µm (matched)
Current mirror loads:    W/L = 5-10µm
```

### 130nm-Specific Design Checklist:

- [ ] Supply voltage: 1.8V (check data sheet for your PDK)
- [ ] Operating temperature: 27°C nominal, verify -40 to 125°C range
- [ ] Minimum gate length: 0.13µm (always use exact value)
- [ ] Check transistor saturation: VDS > VGS - Vt (typically >0.1-0.2V)
- [ ] Include body effect for 130nm (Vt shifts with VSB)
- [ ] Verify layout matching for differential pairs
- [ ] Include metal-1 via connections and layer stack
- [ ] Simulate DC/AC/transient analyses
- [ ] Verify process corners (SS, TT, FF for robustness)
- [ ] Check temperature variation (-40 to 125°C)

### LTspice Simulation Best Practices for 130nm:

```
✅ Use .include technology/130nm-techfile.lib
✅ Specify exact W/L ratios (e.g., W=10u L=0.13u)
✅ Set appropriate DC operating points before AC analysis
✅ Use sufficient resolution: .tran 0 100n 0 10p (10ps steps)
✅ AC sweep: .ac dec 100 1 1G (100 pts/decade, 1Hz-1GHz)
✅ Export results: .print dc v(*) i(*) to file
✅ Use .measure for automated result extraction
✅ Verify convergence in .log file
✅ Check for oscillations in transient
✅ Document all simulation parameters
```

---

## 🎓 Learning Path for 130nm Design

**Stage 1: Fundamentals** → Common Source (basic gain stage)
↓
**Stage 2: Intermediate** → Cascode (high-gain, bandwidth control)
↓
**Stage 3: Advanced** → Differential + Current Mirror (op-amp building blocks)

**For each topology:**
1. Read design guide
2. Review schematic
3. Run DC analysis → verify biasing
4. Run transient analysis → check dynamic response
5. Run AC analysis → obtain frequency response
6. Compare simulations with hand calculations

---

## 📋 Simulation Results Summary Table

For quick reference, each amplifier includes:

| Analysis | File | Parameters |
|----------|------|-----------|
| **DC** | `dc-analysis.txt` | VGS, VDS, ID, Power |
| **Transient** | `transient-analysis.txt` | Rise time, settling, slew rate |
| **AC** | `ac-analysis.txt` | Gain (dB), Bandwidth, Phase |

---

**Ready to Design!** 🎚️⚡

*All designs optimized for 130nm CMOS technology*
*Simulated and verified with LTspice*
*Designed with ElectricBinary*

---

Last Updated: 2026-07-17
Technology Node: 130nm
Analysis Types: DC, Transient, AC

