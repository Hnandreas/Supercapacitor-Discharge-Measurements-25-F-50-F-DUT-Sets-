# Supercapacitor-Discharge-Measurements-25-F-50-F-DUT-Sets-

**⚠️ IMPORTANT:** Please read the [DISCLAIMER](DISCLAIMER.md) before using or distributing any content from this repository.

This repository publishes the raw discharge CSV logs and the derived figures from our supercapacitor characterization campaign. The analysis notebooks remain private; the published material captures the breadth of the measurement data.

## Table of Contents

- [Linked References](#linked-references)
- [Experimental Setup and Methodology](#experimental-setup-and-methodology)
- [Dataset Structure](#dataset-structure)
- [Measurement Campaign Overview](#measurement-campaign-overview)
- [File Format](#file-format)
- [Figures](#figures)
- [Citation](#citation)
- [License](#license)

## Linked References
- **50 F Measurements (Validation Set):** 
  - [Dataset README & Discharge Curves](50F/README.md) - Eight Vishay 50 F devices tested at three current levels
- **25 F Measurements (Multi-Manufacturer Set):**
  - [Dataset README & Discharge Curves](25F/README.md) - Six manufacturers, each with three 25 F devices tested at three current levels
- **Disclaimer:** [DISCLAIMER.md](DISCLAIMER.md) - Important usage and distribution information
- **Release Notes:** [RELEASE_NOTES.md](RELEASE_NOTES.md) - Version and release information

## Experimental Setup and Methodology

### Sample Overview

This study includes two distinct datasets of commercially available electric double-layer capacitors (EDLCs):

**Dataset 1 (50 F Validation Set):** Eight 50 F, 3.0 V supercapacitors from Vishay, all from the same production batch, used to validate the voltage-dependent capacitance extraction method and quantify batch-level consistency.

**Dataset 2 (25 F Multi-Manufacturer Set):** Eighteen 25 F supercapacitors representing six manufacturers (Eaton, Kyocera, Maxwell, Sech, Vishay, and Würth Elektronik), with three devices per manufacturer from the same batch. All devices are rated at 3.0 V except Würth Elektronik (2.7 V).

All samples were stored in a climate-controlled environment at 21°C ± 2°C prior to testing to minimize thermal and aging effects.

### Test Equipment and Setup

The laboratory setup follows IEC 62391-1 and IEC 62576 standardized test procedures for capacitance and equivalent series resistance (ESR) evaluation. The measurement system comprises:

- **DC Power Supply** - for constant-current charging and voltage holding phases
- **Electronic Load** - for constant-current discharge testing
- **Data Acquisition System** (PicoLog) - for precise voltage logging
- **Custom Low-Impedance Test Fixture** - with four-wire Kelvin connections to minimize parasitic effects and ensure accurate measurements

### Measurement Procedure

Each measurement cycle follows the standardized three-phase IEC sequence:

1. **Constant-current charging (I_ch)** - Device charged to rated voltage U_r
2. **Voltage holding** - Maintained at U_r for 30 minutes to ensure charge stabilization (5 minutes for Methode 1B)
3. **Constant-current discharge (I_dch)** - Discharged at constant current down to target voltage (typically 0.1 × U_r)

All measurements were performed under controlled laboratory conditions with careful attention to IEC compliance.

### Test Conditions

**50 F Dataset (Vishay):**
- Method 1A Class 2 current: 0.06 A
- Method 1A Class 3 current: 0.60 A
- Method 1B Class 3-4-5: 3.41 A (95% efficiency criterion)
- Total: 24 discharge curves (8 DUTs × 3 currents)

**25 F Dataset (Multi-Manufacturer):**
- Method 1A Class 2: 0.03 A (0.027 A for Würth Elektronik)
- Method 1A Class 3: 0.30 A (0.27 A for Würth Elektronik)
- Method 1A Class 4: 3.0 A (2.7 A for Würth Elektronik)
- Total: 54 discharge curves (6 manufacturers × 3 DUTs × 3 currents)

All DUTs were charged according to IEC specifications with 95% charge efficiency. Method 1B discharges were excluded from the multi-manufacturer set to ensure comparability, as these currents vary based on each device's rated ESR.

### Device Specifications

Main characteristics of tested supercapacitors (from manufacturer datasheets):

| Manufacturer | Dataset | U_r (V) | C_r (F) | ESR_n (mΩ) | Diameter (mm) | Length (mm) |
|-------------|---------|---------|---------|------------|---------------|-------------|
| Vishay | 1  | 3.0 | 50 | 22 | 18.0 | 35.0 |
| Vishay | 2 | 3.0 | 25 | 34 | 16.0 | 25.0 |
| Eaton | 2 | 3.0 | 25 | 18 | 16.5 | 28.9 |
| Kyocera | 2 | 3.0 | 25 | 50 | 16.0 | 25.0 |
| Maxwell | 2 | 3.0 | 25 | 25 | 16.0 | 25.5 |
| Sech | 2 | 3.0 | 25 | 25 | 16.0 | 25.0 |
| Würth Elektronik | 2 | 2.7 | 25 | 25 | 16.0 | 25.0 |



## Dataset Structure

- `data/25F/` – CSV files for all 25 F devices under test (DUTs)
- `data/50F/` – CSV files for all 50 F DUTs 


## Measurement Campaign Overview

- **50 F Dataset**  
  Eight Vishay DUTs (`DUT1–DUT8`), each recorded at three discharge currents (current levels are encoded in the filenames and headers).

- **25 F Dataset**  
  Manufacturers: Eaton, Kyocera, Maxwell, Sech, Vishay, Würth Elektronik  
  - Three DUTs per manufacturer (`DUT1–DUT3`)  
  - Three discharge currents each  
    - 0.03 A, 0.30 A, 3.0 A for Eaton, Kyocera, Maxwell, Sech, Vishay  
    - 0.027 A, 0.27 A, 2.7 A for Würth Elektronik

## File Format

Each CSV represents a single discharge curve:

- `time_s` – time stamp in seconds  
- `voltage_V` – measured terminal voltage  
- `range_label` / `comment` – operating window (IEC 62391, IEC 62576, 90–20 %, etc.)

## Figures

The `figures/` directory contains ESR-versus-current plots, reconstruction error comparisons, and method-overview charts generated from the published CSV files.

## Citation

If you use these data or figures, please cite both the related paper and the Zenodo record:

- **Paper:** *[A Standard - Aligned Framework for Voltage-Dependent Supercapacitor Characterization]*  
- **Zenodo record:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17392993.svg)](https://doi.org/10.5281/zenodo.17392993)

## License

*(insert the license or usage statement that applies to this dataset)+
