## Data Preprocessing Project

A small workspace for demonstrating end‑to‑end data preprocessing and feature engineering on tabular datasets. It includes:
- Loan approval dataset preprocessing with EDA, encoding, scaling, and outlier handling.
- A completed tutorial workflow on the UCI Adult Income dataset.
- An unsolved/template notebook for practice on the same Adult dataset steps.

### Repository structure
- `Data Preprocessing.ipynb` — Complete walkthrough on the provided loan approval dataset: EDA, feature engineering, encoding, scaling, and outlier treatment (with Seaborn boxplots and IQR/Z‑score checks).
- `loan_approval_dataset.csv` — Local dataset used by `Data Preprocessing.ipynb` containing 4,269 rows and 13 columns (no missing values found during inspection).
- `solution_file.ipynb` — A solved, step‑by‑step preprocessing notebook using the UCI Adult Income dataset (downloaded from the UCI repository). Covers loading, inspecting, cleaning, exploring categorical values, handling duplicates, and more.
- `unsoived_file.ipynb` — An unsolved/template version of the Adult dataset preprocessing with clearly marked TODO steps for practice. Students can implement the same steps shown in `solution_file.ipynb`.

### Dataset details (loan_approval_dataset.csv)
Columns:
- `loan_id` (int): Unique identifier.
- `no_of_dependents` (int)
- `education` (str): Graduate / Not Graduate
- `self_employed` (str): Yes / No
- `income_annum` (int)
- `loan_amount` (int)
- `loan_term` (int) — months
- `cibil_score` (int)
- `residential_assets_value` (int)
- `commercial_assets_value` (int)
- `luxury_assets_value` (int)
- `bank_asset_value` (int)
- `loan_status` (str): Approved / Rejected

Notable preprocessing steps demonstrated in `Data Preprocessing.ipynb`:
- Duplicate and null checks (no missing values reported; duplicates removed if present)
- Column name trimming
- Feature engineering: `income_to_loan_ratio`, `total_asset_value`, `LTV_ratio%`
- Redundant column drop (IDs and decomposed asset columns)
- Categorical encoding via `LabelEncoder` for `education`, `self_employed`, `loan_status`
- Standardization with `StandardScaler` of numeric features
- Outlier analysis (boxplots) and treatment using IQR and Z‑score filtering

### Requirements
- Python 3.9+ recommended
- Packages:
  - numpy
  - pandas
  - scikit‑learn
  - seaborn
  - matplotlib
  - scipy
  - notebook (to run Jupyter locally)

You can install everything quickly:

```bash
pip install numpy pandas scikit-learn seaborn matplotlib scipy notebook
```

### How to clone
```bash
git clone https://github.com/noumanic/data-preprocessing-python.git
cd data-preprocessing-python
```

### How to run the notebooks (Windows PowerShell)
1. (Optional) Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```
2. Install dependencies (see above).
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open and run:
   - `Data Preprocessing.ipynb` to reproduce the loan dataset preprocessing and visualizations.
   - `solution_file.ipynb` to see a completed reference workflow on the Adult dataset.
   - `unsoived_file.ipynb` to practice the same steps (fill in the TODOs).

### Notes on the notebooks
- `Data Preprocessing.ipynb` reads `loan_approval_dataset.csv` from the repository root. Ensure your working directory is this project folder when launching Jupyter.
- The Adult dataset in `solution_file.ipynb`/`unsoived_file.ipynb` is loaded directly from the UCI repository URL at runtime.

### Suggested next steps
- Save intermediate cleaned datasets to CSV/Parquet for downstream modeling.
- Add simple baseline models (e.g., logistic regression, tree‑based) using the engineered features.
- Track experiments and metrics (e.g., with a lightweight ML metadata tracker) if you extend this project.

### Credits
Made by Muhammad Nouman Hafeez (@noumanic)
