# INSE 6450 – Milestone 1
Smart Grocery Assistant

## Dependencies

Python 3.9+

Install required packages:

pip install pandas numpy matplotlib

---

## How to Run the Code

1. (Optional) Generate synthetic datasets:

python src/generate_synthetic_data.py

This will create the CSV files inside the `data/` folder.

2. Run data exploration:

Open the notebook:

notebooks/data_exploration.ipynb

Run all cells from top to bottom.

The notebook reads raw datasets from the `data/` folder using relative paths.

---

## Output Location

All generated outputs are saved in the `outputs/` folder, including:

- pantry_inventory.png
- consumption_hist.png
- avg_weekly_consumption_per_item.png
- data_exploration_summary.csv

The code runs directly from raw data and does not use hard-coded absolute paths.


INSE 6450 – Milestone 2

Smart Grocery Assistant – Restock Prediction Model

Dependencies

Python 3.9+

Install required packages:

pip install pandas numpy matplotlib scikit-learn torch
How to Run the Code

Open the training notebook:

notebooks/restock_training.ipynb

Run all cells from top to bottom.

The notebook:

Loads datasets from the data/ folder using relative paths

Performs feature engineering (last1, last2, roll2, is_piece, essential)

Trains a PyTorch linear regression model

Evaluates baseline vs final model

Measures training efficiency and inference performance

Model Description

Restock Predictor:

Model: Single-layer linear regression (PyTorch)

Input features: 5 engineered features

Output: Predicted next-week demand

Trainable parameters: 6 (5 weights + 1 bias)

Performance Results

Validation (Week 5):

MAE: 1.544

RMSE: 2.173

R²: 0.429

Test (Week 6):

MAE: 1.188

RMSE: 1.642

R²: 0.433

Baseline comparison (rolling average) is included in results_table.csv.

Training Efficiency

Measured on CPU:

Total training time: 0.189 s

Time per epoch: 0.0036 s/epoch

Model parameters: 6

On-disk size: 1.958 KB

FLOPs: ~10 operations per sample

Inference Performance

Measured on CPU (batch size = 16):

Latency (p50): 0.0142 ms

Latency (p90): 0.0252 ms

Throughput: 44,619 samples/sec

Memory footprint: negligible (CPU-only)

Output Location

All generated outputs are saved in the outputs/ folder, including:

results_table.csv

restock_model.pt

learning_curves.png

ablation_baseline_vs_final.csv

The code uses relative paths and avoids hard-coded absolute paths.
