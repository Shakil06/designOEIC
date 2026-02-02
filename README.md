# Optoelectronic Integrated Circuit (OEIC) Design Simulations

This repository contains MATLAB simulation scripts for designing and analyzing various optoelectronic devices as part of the EEE460 project (Group 04). The simulations cover four main optoelectronic components: Quantum Well Lasers, Light Emitting Diodes (LEDs), Photodetectors, and Solar Cells.

## 📋 Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Components](#components)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Device Specifications](#device-specifications)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Authors](#authors)

## 🔬 Overview

Optoelectronic Integrated Circuits (OEICs) combine optical and electronic functions on a single chip. This project provides comprehensive MATLAB simulations for designing and analyzing various optoelectronic devices with detailed performance characterization including:

- **Optical characteristics** (emission spectra, gain curves, wavelength response)
- **Electrical characteristics** (I-V curves, current-voltage relationships)
- **Efficiency metrics** (quantum efficiency, power conversion efficiency)
- **Device-specific parameters** (fill factor, responsivity, detectivity, etc.)

## 📁 Repository Structure

```
designOEIC/
├── src/                                    # Source code directory
│   ├── laser/                             # Laser-related simulations
│   │   ├── EEE460_project_group04_LASER01.m    # Quantum Well Laser simulation
│   │   └── laser.m                             # Alternative laser implementation
│   ├── led/                               # LED simulations
│   │   └── EEE460_project_group04_LED01.m      # LED simulation
│   ├── photodetector/                     # Photodetector simulations
│   │   └── EEE460_project_group04_PhotoDetector01.m  # Photodetector simulation
│   └── solar_cell/                        # Solar cell simulations
│       └── EEE460_project_group04_SolarCell01.m      # Solar Cell simulation
├── data/                                  # Data files and material properties
│   ├── InGaAs.txt                        # InGaAs material optical properties
│   ├── laser.txt                         # Laser material parameters
│   └── sensitivity_GaAs.txt              # GaAs spectral sensitivity data
├── docs/                                  # Documentation
│   └── EEE460_projectReport_group04.pdf  # Detailed project report
├── .gitignore                            # Git ignore file for MATLAB projects
└── README.md                             # This file
```

## 🔧 Components

### 1. **Quantum Well Laser (In₀.₂₁Ga₀.₇₉As)**
   - **File:** `src/laser/EEE460_project_group04_LASER01.m`
   - Simulates quantum well laser behavior
   - Calculates gain coefficient and cavity modes
   - Generates I-V and P-I characteristics
   - Computes various efficiency metrics (slope, EQE, EDQE, IQE, EE, PCE)

### 2. **Light Emitting Diode ((Al₀.₃₆Ga₀.₆₄)₀.₅In₀.₅P)**
   - **File:** `src/led/EEE460_project_group04_LED01.m`
   - Models LED emission characteristics
   - Calculates spontaneous emission rate
   - Determines injection efficiency, radiative efficiency, and extraction efficiency
   - Generates Light-Current (L-I) characteristics

### 3. **Photodetector (InGaAs)**
   - **File:** `src/photodetector/EEE460_project_group04_PhotoDetector01.m`
   - Simulates photodetector response
   - Calculates photocurrent and responsivity
   - Computes quantum efficiency, gain, NEP, and detectivity
   - Generates wavelength-dependent response curves

### 4. **Solar Cell (Si)**
   - **File:** `src/solar_cell/EEE460_project_group04_SolarCell01.m`
   - Models silicon solar cell behavior
   - Analyzes effects of series resistance
   - Calculates fill factor, open-circuit voltage, and short-circuit current
   - Generates I-V and P-V characteristics

## 🛠️ Prerequisites

### Software Requirements
- **MATLAB** R2016b or later (tested with R2019a and newer)
- Required MATLAB Toolboxes:
  - Signal Processing Toolbox (for `gaussmf` function)
  - Statistics and Machine Learning Toolbox (for statistical functions)

### Hardware Requirements
- Minimum 4 GB RAM
- Any modern processor (Intel/AMD)
- Display resolution: 1024x768 or higher (for viewing plots)

## 💻 Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Shakil06/designOEIC.git
   cd designOEIC
   ```

2. **Open MATLAB:**
   Launch MATLAB and navigate to the repository directory

3. **Set the path:**
   ```matlab
   % Add repository to MATLAB path
   addpath(genpath(pwd));
   ```

## 🚀 Usage

### Running Simulations

Each simulation can be run independently. Navigate to the specific source directory and execute the script.

#### Example 1: Running the Laser Simulation

```matlab
% Navigate to the laser directory
cd src/laser

% Run the quantum well laser simulation
run('EEE460_project_group04_LASER01.m')
```

**Expected Output:**
- Gain coefficient vs wavelength plot with cavity modes
- I-V characteristics curve
- P-I (Power-Current) characteristics
- Efficiency parameters displayed in the console

#### Example 2: Running the LED Simulation

```matlab
% Navigate to the LED directory
cd src/led

% Run the LED simulation
run('EEE460_project_group04_LED01.m')
```

**Expected Output:**
- Spontaneous emission rate vs wavelength
- Light-Current characteristics
- I-V characteristics
- Efficiency parameters (injection, radiative, extraction, luminous)

#### Example 3: Running the Photodetector Simulation

```matlab
% Navigate to the photodetector directory
cd src/photodetector

% Run the photodetector simulation
run('EEE460_project_group04_PhotoDetector01.m')
```

**Expected Output:**
- Photocurrent vs wavelength
- Responsivity vs wavelength
- V-I characteristics
- Gain vs wavelength
- NEP and detectivity calculations

#### Example 4: Running the Solar Cell Simulation

```matlab
% Navigate to the solar cell directory
cd src/solar_cell

% Run the solar cell simulation
run('EEE460_project_group04_SolarCell01.m')
```

**Expected Output:**
- I-V characteristics for different series resistances
- P-V characteristics
- Maximum power vs series resistance
- V_oc, I_sc, and Fill Factor vs series resistance plots

### Modifying Parameters

Each simulation file contains clearly commented sections for material properties and simulation parameters. You can modify these values to simulate different devices or operating conditions.

Example (from laser simulation):
```matlab
%% Material Properties(In1-xGaxAs) x = 0.79
me          = 0.054*m0;               % elec effective mass
mh          = 0.4*m0;                 % hole effective mass
mu_e        = 6953;                   % electron mobility
mu_h        = 400;                    % hole mobility
Eg          = 1.13;                   % Bandgap
Nd          = 5e17;                   % n type doping profile
Na          = 1e15;                   % p type doping profile
```

## 📊 Device Specifications

### Laser (In₀.₂₁Ga₀.₇₉As Quantum Well)

| Parameter | Value | Unit |
|-----------|-------|------|
| Wavelength | 1100 | nm |
| Cavity Length (L) | 0.5 | mm |
| Active Region Width (w) | 8 | μm |
| Active Region Thickness (d) | 0.2 | μm |
| n-type Doping (Nd) | 5×10¹⁷ | cm⁻³ |
| p-type Doping (Na) | 1×10¹⁵ | cm⁻³ |
| Bandgap Energy (Eg) | 1.13 | eV |
| Reflectivity R1 | 100 | % |
| Reflectivity R2 | 70 | % |

**Key Outputs:**
- Threshold current (Ith)
- Gain coefficient
- Slope efficiency
- External/Internal quantum efficiency
- Power-Current characteristics

### LED ((Al₀.₃₆Ga₀.₆₄)₀.₅In₀.₅P)

| Parameter | Value | Unit |
|-----------|-------|------|
| Wavelength Range | 410-700 | nm |
| n-type Doping (Nd) | 5×10¹⁷ | cm⁻³ |
| p-type Doping (Na) | 1×10¹⁵ | cm⁻³ |
| Bandgap Energy (Eg) | 2.13 | eV |
| Active Area | 1×10⁻² | cm² |
| Refractive Index | 2.5 | - |

**Key Outputs:**
- Emission spectrum
- Injection efficiency
- Radiative recombination efficiency
- Extraction efficiency
- Luminous efficiency
- Light-Current characteristics

### Photodetector (InGaAs)

| Parameter | Value | Unit |
|-----------|-------|------|
| Active Area | 20 | cm² |
| Wavelength Range | 0.2-3.0 | μm |
| p-layer Thickness (wp) | 0.005 | μm |
| Intrinsic Layer Thickness (wi) | 1 | μm |
| Incident Power (I0) | 500 | W/m² |
| Load Resistance (RL) | 10 | Ω |

**Key Outputs:**
- Photocurrent vs wavelength
- Responsivity
- Quantum efficiency
- Photoconductive gain
- NEP (Noise Equivalent Power)
- Detectivity (D*)

### Solar Cell (Si)

| Parameter | Value | Unit |
|-----------|-------|------|
| n-type Doping (Nd) | 5×10¹⁷ | cm⁻³ |
| p-type Doping (Na) | 1×10¹⁵ | cm⁻³ |
| Bandgap Energy (Eg) | 1.12 | eV |
| Active Area | 1×10⁻² | cm² |
| Photocurrent (Iph) | 20 | mA |
| Irradiation | 1000 | W/m² |
| Series Resistance | 0.01-0.05 | Ω |

**Key Outputs:**
- Open-circuit voltage (Voc)
- Short-circuit current (Isc)
- Fill factor (FF)
- Maximum power point
- I-V and P-V characteristics
- Series resistance effects

## 📈 Results

Simulation results include:

1. **Graphical Outputs:**
   - Spectral characteristics (emission, absorption, gain)
   - Current-Voltage (I-V) curves
   - Power-Current (P-I) curves
   - Efficiency vs parameter plots

2. **Numerical Results:**
   - Device efficiencies (quantum, power conversion, etc.)
   - Operating points (threshold current, peak wavelength, etc.)
   - Performance metrics (responsivity, detectivity, fill factor, etc.)

For detailed analysis and theoretical background, please refer to the [project report](docs/EEE460_projectReport_group04.pdf).

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add new feature'`)
5. Push to the branch (`git push origin feature/improvement`)
6. Create a Pull Request

## 📄 License

This project is part of an academic course (EEE460) and is intended for educational purposes. Please contact the authors for usage permissions.

## 👥 Authors

**Group 04 - EEE460 Project**

For questions or collaboration opportunities, please open an issue on GitHub.

## 📚 References

1. Wilson, J. and Hawkes, J., "Optoelectronics: An Introduction"
2. Kasap, S.O., "Optoelectronics and Photonics: Principles and Practices"
3. Bhattacharya, P., "Semiconductor Optoelectronic Devices"

## 📝 Citation

If you use this code in your research, please cite:

```bibtex
@misc{designOEIC2024,
  author = {Group 04},
  title = {Optoelectronic Integrated Circuit Design Simulations},
  year = {2024},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/Shakil06/designOEIC}}
}
```

---

**Last Updated:** February 2026

For more information, please refer to the [detailed project report](docs/EEE460_projectReport_group04.pdf).
