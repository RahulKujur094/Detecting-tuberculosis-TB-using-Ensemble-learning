# Tuberculosis

Tuberculosis Detection using Model Ensemble 🫁🧠
This repository presents a machine learning solution for detecting tuberculosis (TB) using ensemble learning. The pipeline involves training three different models and combining their predictions through averaging to produce a final submission file.

📁 Repository Contents
bash
Copy
Edit
.
├── tb1.ipynb                # First model notebook
├── tb2.ipynb                # Second model notebook
├── tb3.ipynb                # Third model notebook
├── FinalAveraging.py       # Script to average predictions and generate final submission
├── README.md               # Project documentation
└── README_instructions.txt # Instructions outlining the project approach
🧠 Project Overview
To improve prediction robustness and accuracy, we created three different machine learning models trained on the same TB dataset. Each model produces a CSV file with predicted probabilities. These predictions are then combined via simple averaging, and the final output is binarized (threshold = 0.5) to generate the final submission file.

✅ Key Steps:
Train 3 independent TB detection models (tb1.ipynb, tb2.ipynb, tb3.ipynb)

Each model outputs predictions to a CSV file

FinalAveraging.py:

Loads the 3 prediction files

Averages the Target values

Applies thresholding to convert to binary labels

Saves the final result to final_submission.csv

🛠 Requirements
Install the following packages:

bash
Copy
Edit
pip install numpy pandas scikit-learn
If you're using GPU-based deep learning models, you may also need:

bash
Copy
Edit
pip install tensorflow or pip install torch torchvision
(Specific dependencies may vary based on model architecture in the notebooks.)

🚀 How to Run
Train the models
Run each of the following notebooks to generate 3 prediction CSV files:

tb1.ipynb → outputs tb_predictions1.csv

tb2.ipynb → outputs tb_predictions2.csv

tb3.ipynb → outputs tb_predictions3.csv

Set correct file paths
In FinalAveraging.py, set the paths to your prediction files accordingly:

python
Copy
Edit
csv_files = [
    "path/to/tb_predictions1.csv",
    "path/to/tb_predictions2.csv",
    "path/to/tb_predictions3.csv"
]
Run the ensemble script

bash
Copy
Edit
python FinalAveraging.py
Output:

final_submission.csv — the averaged and binarized predictions ready for submission.

📊 Output Format
The final submission CSV contains two columns:

Id: Sample identifier

Target: 0 (No TB) or 1 (TB Present)

📌 Notes
The final ensemble prediction uses a hard voting mechanism (threshold = 0.5).

Ensure the predictions in the CSV files are aligned and sorted identically before averaging.

✨ Future Work
Experiment with weighted averaging

Explore stacking or blending approaches

Use additional ensemble techniques such as bagging and boosting

📜 License
This project is open-source and available under the MIT License
