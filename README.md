
# UAV LoS/NLoS Ray-Tracing Database

This repository provides a ray-tracing-based dataset for research on UAV Line-of-Sight (LoS) and Non-Line-of-Sight (NLoS) classification and localization.

The dataset contains MATLAB-generated ray-level and link-level simulation results, along with processed CSV tables for machine learning experiments.

## 1. Download

The complete dataset is distributed as **`uav_los_nlos_database.zip`** through [GitHub Releases](https://github.com/WENHAO-SHEN320/uav_los_nlos_database/releases).

1. Open the **Releases** page.
2. Download **`uav_los_nlos_database.zip`** from the release assets.
3. Extract the archive and refer to the included `README.md` for detailed dataset information.

**Note:** Download the dataset archive from the release assets rather than GitHub's automatically generated **Source code (zip)** file, which does not contain the complete dataset.

## 2. Dataset Overview

- **Development dataset:** Trajectories T01–T03, simulated with maximum reflection limits of three and five.
- **Held-out evaluation dataset:** Trajectories T04–T05, generated with a maximum of five reflections and reserved for independent evaluation.
- **Data formats:** Ray-level and link-level CSV tables, instantaneous and five-point sequential machine learning datasets, and metadata.

## 3. MATLAB Quick Start

After extracting the archive, set `root` to the directory containing `load_uav_database.m` and the dataset folders:

```matlab
root = "/path/to/extracted_uav_database";
addpath(root);

T = load_uav_database(root, ...
    "development/reflection5/instantaneous_compact.csv");
```

The CSV files can also be loaded directly using MATLAB's built-in `readtable` function.

## 4. Data Integrity

The archive includes `manifest.json`, which records file paths, sizes, table dimensions, and SHA-256 checksums for the CSV datasets.

## 5. Research Use

The dataset is generated through ray-tracing simulations and should not be interpreted as measured radio-channel observations.

When using the dataset in research, please identify the corresponding release version to support reproducibility.
