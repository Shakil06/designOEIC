# Running the Simulations

This guide provides quick-start instructions for running each simulation.

## Prerequisites

Make sure you have MATLAB installed with the required toolboxes:
- Signal Processing Toolbox
- Statistics and Machine Learning Toolbox

## Running Individual Simulations

### Method 1: Using MATLAB GUI

1. Open MATLAB
2. Navigate to the specific simulation directory using the "Current Folder" panel
3. Double-click on the `.m` file to open it
4. Click "Run" or press F5

### Method 2: Using MATLAB Command Window

```matlab
% For Laser Simulation
cd src/laser
run('EEE460_project_group04_LASER01.m')

% For LED Simulation  
cd src/led
run('EEE460_project_group04_LED01.m')

% For Photodetector Simulation
cd src/photodetector
run('EEE460_project_group04_PhotoDetector01.m')

% For Solar Cell Simulation
cd src/solar_cell
run('EEE460_project_group04_SolarCell01.m')
```

### Method 3: Run All Simulations

To run all simulations sequentially, you can create a master script or run them one by one:

```matlab
% Save current directory
originalDir = pwd;

% Run Laser simulation
cd('src/laser')
run('EEE460_project_group04_LASER01.m')
cd(originalDir)

% Run LED simulation
cd('src/led')
run('EEE460_project_group04_LED01.m')
cd(originalDir)

% Run Photodetector simulation
cd('src/photodetector')
run('EEE460_project_group04_PhotoDetector01.m')
cd(originalDir)

% Run Solar Cell simulation
cd('src/solar_cell')
run('EEE460_project_group04_SolarCell01.m')
cd(originalDir)

disp('All simulations completed!')
```

## Troubleshooting

### Issue: "File not found" error for data files

**Solution:** Make sure you're running the scripts from their respective directories. The scripts use relative paths to access data files.

### Issue: "Undefined function 'gaussmf'"

**Solution:** Install the Fuzzy Logic Toolbox or Signal Processing Toolbox.

### Issue: Plots not showing

**Solution:** Check if figure windows are hidden. Type `shg` (show graphics) in the command window.

## Understanding the Output

### Laser Simulation
- **Plot 1:** Gain coefficient vs wavelength with cavity modes
- **Plot 2:** I-V characteristics
- **Plot 3:** P-I (Power-Current) characteristics
- **Console:** Efficiency metrics

### LED Simulation
- **Plot 1:** Spontaneous emission rate vs wavelength
- **Plot 2:** Light-Current characteristics  
- **Plot 3:** I-V characteristics
- **Console:** Efficiency values (injection, radiative, extraction, luminous)

### Photodetector Simulation
- **Plot 1:** Photocurrent vs wavelength
- **Plot 2:** Responsivity vs wavelength
- **Plot 3:** Voltage vs Current
- **Plot 4:** Gain vs wavelength
- **Plot 5:** I-V characteristics under illumination

### Solar Cell Simulation
- **Plot 1:** I-V characteristics for different series resistances
- **Plot 2:** P-V characteristics
- **Plot 3:** Maximum power vs series resistance
- **Plot 4:** Open-circuit voltage vs series resistance
- **Plot 5:** Short-circuit current vs series resistance
- **Plot 6:** Fill factor vs series resistance

## Saving Results

To save figures:
```matlab
% Save current figure
savefig('figure_name.fig')
% Or as image
print('figure_name.png', '-dpng', '-r300')
```

To export data:
```matlab
% Save workspace variables
save('simulation_results.mat')
```
