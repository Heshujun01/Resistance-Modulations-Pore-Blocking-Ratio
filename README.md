# Resistance-Modulations-Pore-Blocking-Ratio
access_resistance_project: Pore Blocking Ratio Calculation and Current Time-Domain Plot — using T40 as an example. 
# Nanopore/Ion Channel Event Analysis: T40 Dataset

This repository provides a reproducible pipeline for analyzing single-channel blocking events in the **T40 dataset**. The core component is the Jupyter Notebook `T40(file_path).ipynb`, which processes raw electrophysiology recordings to detect blocking events, compute key biophysical parameters (e.g., blocking ratio, dwell time), and export results for further analysis.

> ⚠️ **Note**: Raw data files (e.g., `T40_+140mV.dat`) are not included due to size or sensitivity.

------

## 1. System Requirements

###  Software Dependencies

Install all dependencies via:

```bash
pip install -r requirements.txt
```

### Tested Environment

- **Python**: 3.12
- **OS**: Windows 11 / Ubuntu 22.04
- **Hardware**: Standard desktop (Intel i5+, 16 GB RAM)

### Required Input

- One or more `.dat` files from the T40 experiment series (e.g., recorded at +140 mV, +160 mV, +180 mV).

------


## 2. Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/Heshujun01/Resistance-Modulations-Pore-Blocking-Ratio.git
cd Resistance-Modulations-Pore-Blocking-Ratio
pip install -r requirements.txt
```
> **Typical installation time**: ~2 minutes.
## 3. Running the Analysis

### Step 1: Prepare Data

Place your T40 `.dat` files in this directory (e.g., `T40_+100mV.dat`).

### Step 2: Run `T40(file_path).ipynb`

1. Open `T40(file_path).ipynb` in Jupyter.
2. Update the `file_path` variable to point to your `.dat` file.
3. Run all cells.

**Output**: A `.npz` file (e.g., `T40_results.npz`) containing:

- `blocking_ratio`: Pore-blocking ratio ($\frac{event\_amplitude}{baseline}$)
- `dwell_time`: Duration of each blocking event (seconds)
- `voltage`: Applied voltage (mV)
- `baseline_level`: Estimated baseline current
- `event_start`, `event_end`: Timestamps of detected events

**Runtime**: ~1–2 minutes per file.

------

## 4. Using Your Own Data

1. Replace the example `file_path` in the notebook with your T40 `.dat` file.
2. The pipeline automatically handles baseline drift correction and event detection.
3. The output `.npz` file can be used for:
   - Plotting distributions (e.g., blocking ratio vs. voltage)
   - Comparing with other datasets (e.g., D10, G6P4D11K)
   - Statistical modeling

------

## 5. Project Structure

```
Resistance-Modulations-Pore-Blocking-Ratio/
├── T40(file_path).ipynb        # Main analysis notebook
├── pySNA.py                    # Core functions (baseline correction, event detection)
├── requirements.txt            # Reproducible dependency list
└── README.md                   # This file
```
