# Brightness and Contrast Guided Adaptive Enhancement for Low-Light Images (BCGAE)

## Project Overview

This project implements and evaluates a brightness- and contrast-guided adaptive enhancement method for low-light images. The proposed BCGAE method combines gamma correction and Contrast Limited Adaptive Histogram Equalization (CLAHE), selecting parameters using image brightness and contrast statistics.

The project compares BCGAE with four conventional image enhancement methods under different levels of low-light degradation.

## Objectives

* Study traditional low-light image enhancement techniques.
* Implement brightness- and contrast-guided parameter selection.
* Compare enhancement performance at mild, moderate, and severe degradation levels.
* Evaluate image quality using quantitative metrics and visual comparisons.
* Analyze the trade-off between enhancement performance and processing time.

## Enhancement Methods

1. Histogram Equalization
2. Gamma Correction
3. Contrast Limited Adaptive Histogram Equalization (CLAHE)
4. Fixed Gamma Correction + CLAHE
5. Proposed BCGAE

## Methodology

The BCGAE pipeline measures the input image's mean luminance and luminance standard deviation. It uses predefined thresholds to select a gamma value and CLAHE clip limit, then applies gamma correction followed by CLAHE on the luminance channel.

## Experimental Setup

* Original images: 10
* Synthetic degradation levels: Mild, Moderate, Severe
* Low-light test inputs: 30
* Enhancement methods: 5
* Total method evaluations: 150

The original images serve as references for evaluating the enhanced results.

## Evaluation Metrics

* **MSE:** Mean Squared Error
* **PSNR:** Peak Signal-to-Noise Ratio
* **SSIM:** Structural Similarity Index
* **Entropy:** Describes the distribution of intensity information
* **Contrast:** Measured using luminance standard deviation
* **Processing Time:** Measures computational runtime

## Repository Contents

* `BCGAE_Low_Light_Enhancement.ipynb` — Jupyter Notebook containing the implementation and experiments.
* `Results/` — Quantitative graphs and visual comparison results.

## Requirements

Python 3.10 or a compatible Python environment with the packages listed in `requirements.txt`.

## How to Run

1. Clone or download this repository.
2. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```
3. Open `BCGAE_Low_Light_Enhancement.ipynb` in Jupyter Notebook.
4. Ensure the dataset and file paths match your local setup.
5. Run the notebook cells in order.

## Limitations

* The evaluation uses synthetically darkened images.
* The experiment uses ten original images.
* The parameter-selection rules are heuristic and have not been established as universally optimal.
* The method may introduce visual artifacts and has a higher processing time than some simpler baselines.

## Disclaimer

BCGAE is a project-specific heuristic based on established image-processing techniques. The results demonstrate its performance on the tested dataset and do not establish universal superiority over existing methods.
