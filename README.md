# 🫁 Tuberculosis Detection using Model Ensemble

This repository presents a machine learning solution for detecting **tuberculosis (TB)** using an **ensemble learning** approach. The pipeline involves training three different models and combining their predictions through simple averaging to produce a final submission file. This approach aims to improve prediction robustness and accuracy.

---





---

## 🧠 Project Overview

To increase the accuracy of tuberculosis prediction, we trained **three different models** on the same TB dataset. Each model independently predicts the probability of TB presence and outputs a `.csv` file with predictions.

These predictions are then **combined using simple averaging**, and a **threshold of 0.5** is applied to convert the averaged probability into binary labels (0 or 1) for final submission.

---

## ✅ Pipeline Summary

1. **Train 3 Independent Models**
   - `tb1.ipynb` → outputs `tb_predictions1.csv`
   - `tb2.ipynb` → outputs `tb_predictions2.csv`
   - `tb3.ipynb` → outputs `tb_predictions3.csv`

2. **Run the Ensemble Script**
   - Edit file paths in `FinalAveraging.py`:
     ```python
     csv_files = [
         "path/to/tb_predictions1.csv",
         "path/to/tb_predictions2.csv",
         "path/to/tb_predictions3.csv"
     ]
     ```
   - Run:
     ```bash
     python FinalAveraging.py
     ```

3. **Final Output**
   - `final_submission.csv` — contains averaged and thresholded predictions.

---

## 🛠 Requirements

Install the required libraries:

```bash
pip install numpy pandas scikit-learn
If your models use deep learning frameworks, install:

bash
Copy
Edit
pip install tensorflow
# or
pip install torch torchvision
🔍 Note: Check the individual notebooks for any model-specific dependencies.

🚀 How to Run
Train all three models:

Run tb1.ipynb, tb2.ipynb, and tb3.ipynb

Each will generate a CSV file with predicted probabilities

Open FinalAveraging.py and update paths to point to your CSV files.

Run the script:

bash
Copy
Edit
python FinalAveraging.py
It will output final_submission.csv with final predictions.

📊 Output Format
The output CSV file final_submission.csv will contain:

Id	Target
1	0
2	1
3	0

Id: Unique sample identifier

Target: 1 (TB detected), 0 (No TB)

📌 Notes
The ensemble prediction uses simple averaging followed by hard thresholding (>= 0.5 → 1, else 0)

Ensure the input prediction CSVs:

Have the same number of rows

Are sorted in the same order by Id

No label leakage is assumed across models.

✨ Future Work
✅ Try weighted averaging for ensemble

🔁 Implement stacking and blending for better performance

🎯 Explore bagging and boosting methods

📈 Perform error analysis on final predictions

🧪 Add confidence intervals or uncertainty quantification

📜 License
This project is open-source and available under the MIT License.
Feel free to use, modify, and distribute it.

🙌 Acknowledgments
Thanks to the open-source medical imaging community

Inspired by Kaggle TB datasets and ensemble modeling practices

Built using Python, NumPy, Pandas, and scikit-learn

markdown
Copy
Edit

Let me know if you'd also like me to generate:
- `LICENSE`
- `requirements.txt`
- `FinalAveraging.py` (if not already written)  
- or help you write the model notebooks (`tb1.ipynb`, etc.)
