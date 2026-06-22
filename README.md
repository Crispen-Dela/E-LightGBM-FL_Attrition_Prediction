# E-LightGBM-FL_Attrition_Prediction
E-LightGBM-FL: Engineered LightGBM with Focal Loss for Student Attrition Prediction in Ghanaian Higher Education  This repository contains the complete implementation for the research proposal: "An Engineered LightGBM-Focal Loss Model for Early Student Attrition Prediction in Ghanaian Higher Education: A SHAP-Explainability Approach.
# E-LightGBM-FL: Engineered LightGBM with Focal Loss for Student Attrition Prediction

## 📌 Project Overview

This repository contains the complete implementation for the research proposal:

**"An Engineered LightGBM-Focal Loss Model for Early Student Attrition Prediction in Ghanaian Higher Education: A SHAP-Explainability Approach"**

This study introduces **E-LightGBM-FL**, an engineered variant of LightGBM that fabricates a custom focal-loss objective function to address severe class imbalance in student attrition prediction. The model is validated on primary field-collected institutional data from Kwame Nkrumah University of Science and Technology (KNUST), Ghana, and enhanced with SHAP-based global and local explanations for actionable early intervention.

---

## 🎯 Research Contribution

| Component | Description |
|-----------|-------------|
| **Engineering Operation** | [F] FABRICATE — Focal Loss objective function integrated into LightGBM |
| **Engineered Model** | E-LightGBM-FL (Engineered LightGBM with Focal Loss) |
| **Novelty** | First combination of LightGBM + Focal Loss for attrition prediction in sub-Saharan African higher education |
| **Dataset** | Primary field-collected KNUST institutional data (n=2,500) |
| **Explainability** | SHAP-based global and local explanations for administrators |

---

## 📂 Repository Structure
E-LightGBM-FL_Attrition_Prediction/
│
├── data/
│   ├── raw/                      # Raw KNUST institutional data (encrypted)
│   └── processed/                # Preprocessed data (train/test splits)
│
├── notebooks/
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_baseline_lightgbm.ipynb      # LOCKED - never modified
│   ├── 03_engineered_lightgbm_fl.ipynb # E-LightGBM-FL implementation
│   └── 04_evaluation_visualisation.ipynb
│
├── src/
│   ├── focal_loss.py             # Custom focal loss implementation
│   ├── model_engineering.py      # E-LightGBM-FL class
│   ├── evaluation.py             # Metrics and significance testing
│   └── shap_explainer.py         # SHAP global/local explanations
│
├── results/
│   ├── baseline_metrics.csv      # LOCKED baseline results (SEED=2026)
│   ├── engineered_metrics.csv    # E-LightGBM-FL results
│   ├── comparison_table.csv      # Formal comparison with deltas
│   └── figures/                  # ROC curves, SHAP plots, confusion matrices
│
├── requirements.txt              # Pinned library versions
├── README.md                     # This file
├── LICENSE                       # MIT License
└── .gitignore                    # Python standard

```

---

## 🚀 Quick Start

### Prerequisites

- Python 3.10.12
- Google Colab Pro (recommended) or local machine with 16GB+ RAM

### Installation

```bash
# Clone repository
git clone https://github.com/[YOUR_USERNAME]/E-LightGBM-FL_Attrition_Prediction.git
cd E-LightGBM-FL_Attrition_Prediction

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

Running the Experiments

1. Data Preprocessing
   ```bash
   jupyter notebook notebooks/01_data_preprocessing.ipynb
   ```
2. Baseline Model (LOCKED - never modify)
   ```bash
   jupyter notebook notebooks/02_baseline_lightgbm.ipynb
   ```
3. Engineered E-LightGBM-FL
   ```bash
   jupyter notebook notebooks/03_engineered_lightgbm_fl.ipynb
   ```
4. Evaluation & Visualisation
   ```bash
   jupyter notebook notebooks/04_evaluation_visualisation.ipynb
   ```

---

🔬 Methodology

Baseline Models

1. Unmodified LightGBM (default cross-entropy loss)
2. XGBoost (default loss)
3. Logistic Regression

Engineered Model: E-LightGBM-FL

The focal loss function is:

```
FL(p_t) = -α_t(1 - p_t)^γ log(p_t)
```

Where:

· p_t = model's estimated probability for the true class
· γ = focusing parameter (set to 2)
· α_t = balancing parameter (set to 0.75 for at-risk class)

Evaluation Metrics

· Accuracy
· Macro F1-Score
· AUC-ROC
· AUC-PR (Primary metric for imbalanced data)
· Recall (At-Risk Class)
· Training Time (seconds)

Statistical Significance

· Wilcoxon Signed-Rank Test (α = 0.05)
· 5-fold stratified cross-validation
· Fixed random seed: SEED = 2026

---

📊 Expected Results Table

Metric Baseline (LightGBM) E-LightGBM-FL Δ Change p-value Sig.
Accuracy 0.XXXX ± 0.XXXX 0.XXXX ± 0.XXXX +0.XXXX 0.XXXX Yes/No
Macro F1 ... ... ... ... ...
AUC-ROC ... ... ... ... ...
AUC-PR ... ... ... ... ...
Recall (At-Risk) ... ... ... ... ...
Training Time (s) ... ... +Xs --- ---

---

📝 Reproducibility

All experiments use:

· Fixed random seed: SEED = 2026
· 5-fold stratified cross-validation
· Identical data splits across baseline and engineered models
· Locked baseline — never modified after first run

Software Versions

Package Version
Python 3.10.12
LightGBM 4.0.0
XGBoost 2.0.0
scikit-learn 1.3.0
SHAP 0.42.0
NumPy 1.24.0
Pandas 2.0.0
Matplotlib 3.7.0
Seaborn 0.12.0

---

🏛️ Ethics & Data

· Ethics Body: KNUST Committee on Human Research, Publications and Ethics (CHRPE)
· Status: Submitted (Reference pending)
· Data: De-identified KNUST institutional records (n=2,500)
· Anonymisation: Direct identifiers removed at source by Registrar's Office
· Storage: Encrypted on KNUST servers; access restricted to research team

---

📄 Citation

If you use this code or methodology, please cite:

```
[Author Name]. (2026). E-LightGBM-FL: Engineered LightGBM with Focal Loss 
for Student Attrition Prediction. GitHub Repository.
https://github.com/[YOUR_USERNAME]/E-LightGBM-FL_Attrition_Prediction

