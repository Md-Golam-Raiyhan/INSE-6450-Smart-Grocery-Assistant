# INSE 6450 – Milestone 3
Smart Grocery Assistant – Robustness, Monitoring, and Adaptation

## Dependencies

Python 3.9+

Install required packages:

pip install pandas numpy matplotlib scikit-learn torch

---

## How to Run the Code

Open the robustness and monitoring notebook:

notebooks/robustness_monitoring.ipynb

Run all cells from top to bottom.

The notebook:

- Loads datasets from the `data/` folder using relative paths
- Evaluates model robustness using noise perturbations
- Simulates adversarial input perturbations
- Performs drift detection using Population Stability Index (PSI)
- Generates monitoring metrics and dashboards
- Simulates model adaptation through retraining on drifted data

The notebook uses the trained model generated in Milestone 2 (`restock_model.pt`).

---

## Model Description

Restock Predictor:

Model: Single-layer linear regression (PyTorch)

Input features:

- last1
- last2
- roll2
- is_piece
- essential
- pantry_qty

Output:

Predicted next-week grocery demand.

Trainable parameters: **7 (6 weights + 1 bias)**

The additional feature (`pantry_qty`) was introduced in Milestone 3 to incorporate pantry inventory information for improved robustness analysis.

---

## Robustness Evaluation

The notebook evaluates model robustness under different conditions:

### Noise Robustness

Gaussian noise is added to input features to test prediction stability.

Metrics compared:

- MAE
- RMSE
- R²

Performance degradation under noise is measured and visualized.

---

### Adversarial Perturbation

Feature perturbations simulate adversarial or abnormal inputs to evaluate model sensitivity.

The model predictions under perturbed inputs are compared against the baseline model predictions.

---

## Monitoring and Drift Detection

The notebook simulates a monitoring pipeline that detects data drift.

Drift detection is performed using:

Population Stability Index (PSI)

Key monitored features include:

- last1
- last2
- roll2
- pantry_qty

If PSI exceeds threshold levels, retraining can be triggered.

---

## Adaptation and Retraining

The notebook simulates model adaptation by:

- Introducing synthetic drift into input data
- Retraining the model on updated data
- Comparing performance before and after retraining

Metrics evaluated:

- MAE
- RMSE
- R²

This demonstrates how the system adapts to evolving grocery consumption patterns.

---

## Output Location

All generated outputs are saved in the `outputs/` folder, including:

- monitoring_dashboard.png
- rolling_mae_plot.png
- adaptation_performance_comparison.png
- psi_drift_scores.csv
- feature_distribution_comparison.png

These outputs visualize robustness evaluation, drift detection, and adaptation performance.

---

The code uses relative paths and avoids hard-coded absolute paths.
