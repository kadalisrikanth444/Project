# Project
# Flood Change Detection 2025 over Punjab region

## Project Overview
This repository implements a workflow for detecting flood-induced changes in Punjab, India, during the 2025 monsoon season using Google Earth Engine (GEE). It leverages:
- SAR (Sentinel-1): Backscatter difference for all-weather flood mapping.
- Optical (Sentinel-2): NDWI (Normalized Difference Water Index) for cloud-free water detection.
- Fusion: Logical OR of SAR and optical masks for robust inundation mapping.

Key features:
- Pre- and post-flood mosaics (June-July 2025 pre-flood; August-September 2025 post-flood).
- Auxiliary masking (slope < 10°, exclude permanent water bodies).
- Area statistics and confusion matrix for validation.

Study Area: A rectangular ROI in Punjab (~932 km², centered at [31.16, 75.02]).

Results Summary: Detected ~51.81 km² (5.56%) inundation via SAR (run notebook for latest).

This project is designed for reproducibility in Colab/GEE environments.

## Prerequisites
- Google Earth Engine account (authenticate via `ee.Authenticate()`).
- Python 3.8+ with Jupyter/Colab.
- Google Drive for exports.

## Steps to Run
1. Authenticate GEE:
- Run the first cell in `notebooks/Flood_Analysis_Punjab.ipynb` for authentication.

2. Run the Notebook:
- Open `notebooks/Flood_Analysis_Punjab.ipynb` in Colab/Jupyter.
- Execute all cells. It will:
  - Process SAR/Optical data.
  - Generate visualizations (interactive map).
  - Compute/export change masks and confidences to Google Drive (`Flood_Change_Detection` folder).
  - Print area stats and export samples to `output/`.
- Adjust dates/thresholds in the notebook for custom runs.

