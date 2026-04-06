INSE 6450 – Milestone 4
Smart Grocery Assistant — Continual Learning & Human-in-the-Loop
Dependencies

Python 3.9+

Install required packages:

pip install numpy pandas matplotlib scikit-learn torch

(Optional but recommended)

pip install seaborn
How to Run the Code

Open the notebook:

notebooks/continual.ipynb

Run all cells from top to bottom.

The notebook performs:

Model loading
Incoming data simulation
Drift detection
Human-in-the-loop simulation
Continual learning / retraining
Performance comparison
Model update and saving
Summary results generation
Run Commands (Optional CLI Execution)

If running using command line:

jupyter notebook notebooks/continual.ipynb

or in Google Colab:

Upload continual.ipynb
Run all cells sequentially
Output Location

All generated outputs are saved in the outputs/ folder.

Generated files include:

Continual Learning Outputs
continual_learning_results.csv
continual_learning_performance.png
Monitoring Outputs
drift_detection_results.csv
feature_distribution_comparison.png
Adaptation Results
adaptation_performance_comparison.png
Project Summary
project_summary_table.csv
Models

Updated models are saved in:

models/

Generated model files:

restock_model.pt — Base model
restock_model_updated.pt — Continually updated model
Notebook Workflow

The notebook follows this pipeline:

Load trained model
Simulate new incoming data
Detect drift
Select uncertain samples
Simulate human feedback
Retrain model
Compare performance
Save updated model
Generate summary results
Reproducibility
Relative paths used
No hard-coded absolute paths
Random seed set for reproducibility
Expected Runtime
Total runtime: ~1–2 minutes
Works on CPU (no GPU required)
