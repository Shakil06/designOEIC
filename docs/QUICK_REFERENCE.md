# Quick Reference Guide

## Device Materials at a Glance

| Device | Material | Wavelength | Application |
|--------|----------|------------|-------------|
| **Laser** | In₀.₂₁Ga₀.₇₉As | 1100 nm | Optical communication, sensing |
| **LED** | (Al₀.₃₆Ga₀.₆₄)₀.₅In₀.₅P | 410-700 nm (visible) | Displays, lighting |
| **Photodetector** | InGaAs | 0.2-3.0 μm | Optical receivers, imaging |
| **Solar Cell** | Si | ~1100 nm | Photovoltaic energy conversion |

## Key Parameters Quick Reference

### Universal Constants (Used in All Simulations)
```matlab
m0 = 9.1e-31;        % Electron rest mass (kg)
q = 1.6e-19;         % Electronic charge (C)
kb = 1.38e-23;       % Boltzmann constant (J/K)
h = 6.6626e-34;      % Planck's constant (J·s)
c = 3e8;             % Speed of light (m/s)
T = 300;             % Temperature (K)
```

### Laser Parameters
```matlab
lambda0 = 1100e-9;   % Wavelength (m)
L = 0.5;             % Cavity length (mm)
w = 8e-6;            % Width (m)
d = 0.2e-6;          % Thickness (m)
R1 = 1;              % Front mirror reflectivity
R2 = 0.7;            % Back mirror reflectivity
Eg = 1.13;           % Bandgap (eV)
```

### LED Parameters
```matlab
lambda = 410:5:700;  % Wavelength range (nm)
Eg = 2.13;           % Bandgap (eV)
nr1 = 2.5;           % Refractive index
A = 1e-2;            % Active area (cm²)
```

### Photodetector Parameters
```matlab
A = 20;              % Active area (cm²)
wp = 0.005;          % p-layer thickness (μm)
wi = 1;              % Intrinsic layer thickness (μm)
I0 = 500;            % Incident power (W/m²)
RL = 10;             % Load resistance (Ω)
```

### Solar Cell Parameters
```matlab
A = 1e-2;            % Active area (cm²)
Iph = 20;            % Photocurrent (mA)
I = 1000;            % Irradiation (W/m²)
Rs = [0.01:0.01:0.05]; % Series resistance (Ω)
```

## Common Efficiency Formulas

### Quantum Efficiency (η_q)
```
η_q = (Number of output photons/electrons) / (Number of input photons/electrons)
```

### Power Conversion Efficiency (η_p)
```
η_p = P_out / P_in
```

### External Quantum Efficiency (EQE)
```
η_EQE = (q × P_out) / (I × E_g)
```

### Internal Quantum Efficiency (IQE)
```
η_IQE = 1 / (1 + τ_r/τ_nr)
```

### Fill Factor (FF) - Solar Cells
```
FF = (V_mp × I_mp) / (V_oc × I_sc)
```

## Typical Output Values

### Laser (In₀.₂₁Ga₀.₇₉As)
- Threshold current: ~0.5-2 mA
- Slope efficiency: 0.3-0.6 W/A
- External quantum efficiency: 20-40%
- Operating wavelength: ~1100 nm

### LED ((Al₀.₃₆Ga₀.₆₄)₀.₅In₀.₅P)
- Peak wavelength: ~590-620 nm
- Injection efficiency: 60-80%
- Extraction efficiency: 10-30%
- Luminous efficiency: 5-15%

### Photodetector (InGaAs)
- Responsivity: 0.6-0.9 A/W (at 1.55 μm)
- Quantum efficiency: 70-95%
- Dark current: nA-μA range
- Detectivity: 10¹¹-10¹³ cm·Hz^(1/2)/W

### Solar Cell (Si)
- Open-circuit voltage: 0.6-0.7 V
- Short-circuit current: 30-40 mA/cm²
- Fill factor: 0.7-0.85
- Efficiency: 15-20%

## File Structure Reference

```
designOEIC/
├── src/
│   ├── laser/           → Laser simulations
│   ├── led/             → LED simulations
│   ├── photodetector/   → Photodetector simulations
│   └── solar_cell/      → Solar cell simulations
├── data/
│   ├── InGaAs.txt       → n, k values for InGaAs
│   └── sensitivity_GaAs.txt → Spectral sensitivity
├── docs/
│   ├── *.pdf            → Project reports
│   └── *.md             → Documentation
└── archive/
    └── laser_draft.txt  → Incomplete files (reference only)
```

## Common MATLAB Commands

```matlab
% Change directory
cd src/laser

% Run a script
run('script_name.m')

% Clear workspace
clear all
clc

% Save figure
savefig('myplot.fig')
print('myplot.png', '-dpng')

% Save data
save('results.mat')

% Load data
load('results.mat')

% Export data to text
writematrix(data, 'output.txt')
```

## Data File Formats

### InGaAs.txt
```
Column 1: Wavelength (μm)
Column 2: Refractive index (n)
Column 3: Extinction coefficient (k)
```

### sensitivity_GaAs.txt
```
Column 1: Wavelength (nm)
Column 2: Relative sensitivity
Column 3: Additional parameter
```

## Modifying Simulations

### To Change Material Properties:
Look for sections marked with `%% Material Properties`

### To Change Simulation Range:
Modify variables like:
```matlab
V = 0:0.001:2;          % Voltage range
lambda = 410:5:700;     % Wavelength range
I = 1:5:50;             % Current range
```

### To Change Doping:
```matlab
Nd = 5e17;              % n-type doping (cm⁻³)
Na = 1e15;              % p-type doping (cm⁻³)
```

## Getting Help

1. Check the main README.md
2. Review the project report in docs/
3. Consult MATLAB documentation: `help function_name`
4. Open an issue on GitHub

## Useful MATLAB Functions Used

- `dlmread()` - Read numeric data from file
- `gaussmf()` - Gaussian membership function
- `interp1()` - 1D interpolation
- `fzero()` - Find function zeros
- `exp()`, `log()` - Exponential and logarithm
- `plot()`, `stem()` - Plotting functions
