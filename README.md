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

### Version control and GitHub
Use the commands below to initialize a repository in this folder and push it to GitHub.

#### One‑time Git setup (global; skip if already configured)
```bash
git config --global user.name "YOUR_NAME"
git config --global user.email "YOUR_EMAIL@example.com"
```

#### Initialize, commit, and push to a new GitHub repository
1. Initialize and make the first commit:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: preprocessing notebooks and dataset"
   ```
2. Create an empty repository on GitHub (via the GitHub UI). Copy its URL.
3. Point your local repo to GitHub and push (HTTPS example):
   ```bash
   git branch -M main
   git remote add origin https://github.com/USERNAME/REPO.git
   git push -u origin main
   ```
   If you use SSH:
   ```bash
   git remote add origin git@github.com:USERNAME/REPO.git
   git push -u origin main
   ```

#### If the remote already exists
```bash
git remote -v
# If needed, update it
git remote set-url origin https://github.com/noumanic/REPO.git
```

---
If you need a `requirements.txt`, a `.gitignore` for notebooks/data, or CI/CD instructions, say the word and I’ll add them.
