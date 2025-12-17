# Supercapacitor-Discharge-Measurements-25-F-50-F-DUT-Sets-

**⚠️ IMPORTANT:** Please read the [DISCLAIMER](DISCLAIMER.md) before using or distributing any content from this repository.

This repository publishes the raw discharge CSV logs and the derived figures from our supercapacitor characterization campaign. The analysis notebooks remain private; the published material captures the breadth of the measurement data.

## Linked References

- **25 F Measurements:** 
  - [Dataset README](25F/README.md) - General information about the 25 F device under test (DUT) dataset
  - [Discharge Curves](25F/measurments.md) - Visual overview of all 25 F discharge measurement curves
- **50 F Measurements:** 
  - [Dataset README](50F/README.md) - General information about the 50 F DUT dataset  
  - [Discharge Curves](50F/measurments.md) - Visual overview of all 50 F discharge measurement curves
- **Disclaimer:** [DISCLAIMER.md](DISCLAIMER.md) - Important usage and distribution information
- **Release Notes:** [RELEASE_NOTES.md](RELEASE_NOTES.md) - Version and release information

## Dataset Structure

- `data/25F/` – CSV files for all 25 F devices under test (DUTs)
- `data/50F/` – CSV files for all 50 F DUTs (eight Vishay samples)
- `figures/` – exported plots (ESR vs. discharge current, voltage reconstruction error, etc.)
- `metadata/` – optional summary tables (e.g., U3/I_dc statistics, ESR aggregates)

## Measurement Campaign Overview

- **25 F family**  
  Manufacturers: Eaton, Kyocera (KEMET), Maxwell, Sech, Vishay, Würth Elektronik  
  - Three DUTs per manufacturer (`DUT1–DUT3`)  
  - Three discharge currents each  
    - ≈0.03 A, 0.30 A, 3.0 A for Eaton, Kyocera (KEMET), Maxwell, Sech, Vishay  
    - 0.027 A, 0.27 A, 2.7 A for Würth Elektronik

- **50 F family**  
  Eight Vishay DUTs (`DUT1–DUT8`), each recorded at three discharge currents (current levels are encoded in the filenames and headers).

## File Format

Each CSV represents a single discharge sweep:

- `time_s` – time stamp in seconds  
- `voltage_V` – measured terminal voltage  
- `current_A` – applied discharge current (signed)  
- `temperature_C` – present when measured  
- `range_label` / `comment` – operating window (IEC 62391, IEC 62576, 90–20 %, etc.)

The accompanying JSON header (`header_data`) stores additional parameters: holding voltage, `U3`, `U3_mean`, `I_dc`, ESR estimates, manufacturer name, DUT identifier, and measurement version.

## Figures

The `figures/` directory contains ESR-versus-current plots, reconstruction error comparisons, and method-overview charts generated from the published CSV files.

## Citation

If you use these data or figures, please cite both the related paper and the Zenodo record:

- **Paper:** *[insert full bibliographic reference here]*  
- **Zenodo record:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17392993.svg)](https://doi.org/10.5281/zenodo.17392993)

## License

*(insert the license or usage statement that applies to this dataset)+