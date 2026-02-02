# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased] - 2026-02-02

### Added
- Comprehensive `README.md` with project overview, setup instructions, and usage examples
- `docs/RUNNING_SIMULATIONS.md` - Detailed guide for running each simulation
- `docs/QUICK_REFERENCE.md` - Quick lookup reference for parameters and formulas
- `.gitignore` file for MATLAB projects to exclude backup and temporary files
- `archive/` directory for incomplete or draft files

### Changed
- **Repository Structure**: Reorganized entire repository into logical folders:
  - `src/` - Source code organized by device type (laser, led, photodetector, solar_cell)
  - `data/` - Data files and material properties
  - `docs/` - Documentation and project reports
  - `archive/` - Archived/incomplete files
- Updated file paths in MATLAB scripts:
  - `src/led/EEE460_project_group04_LED01.m` - Updated path to `../../data/sensitivity_GaAs.txt`
  - `src/photodetector/EEE460_project_group04_PhotoDetector01.m` - Updated path to `../../data/InGaAs.txt`
- Moved `laser.txt` to `archive/laser_draft.txt` (incomplete script, for reference only)

### Removed
- All MATLAB autosave files (`*.asv`):
  - `EEE460_project_group04_LASER01.asv`
  - `EEE460_project_group04_LED01.asv`
  - `EEE460_project_group04_PhotoDetector01.asv`
  - `EEE460_project_group04_SolarCell01.asv`
  - `laser.asv`

### File Structure Before
```
designOEIC/
├── EEE460_project_group04_LASER01.m
├── EEE460_project_group04_LASER01.asv
├── EEE460_project_group04_LED01.m
├── EEE460_project_group04_LED01.asv
├── EEE460_project_group04_PhotoDetector01.m
├── EEE460_project_group04_PhotoDetector01.asv
├── EEE460_project_group04_SolarCell01.m
├── EEE460_project_group04_SolarCell01.asv
├── EEE460_projectReport_group04.pdf
├── InGaAs.txt
├── laser.m
├── laser.asv
├── laser.txt
└── sensitivity_GaAs.txt
```

### File Structure After
```
designOEIC/
├── README.md
├── .gitignore
├── src/
│   ├── laser/
│   │   ├── EEE460_project_group04_LASER01.m
│   │   └── laser.m
│   ├── led/
│   │   └── EEE460_project_group04_LED01.m
│   ├── photodetector/
│   │   └── EEE460_project_group04_PhotoDetector01.m
│   └── solar_cell/
│       └── EEE460_project_group04_SolarCell01.m
├── data/
│   ├── InGaAs.txt
│   └── sensitivity_GaAs.txt
├── docs/
│   ├── EEE460_projectReport_group04.pdf
│   ├── QUICK_REFERENCE.md
│   └── RUNNING_SIMULATIONS.md
└── archive/
    └── laser_draft.txt
```

## [1.0.0] - 2024-03-30

### Added
- Initial commit with MATLAB simulation files
- Laser, LED, Photodetector, and Solar Cell simulations
- Material property data files
- Project report PDF

---

**Note**: This CHANGELOG follows the [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) format.
