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
