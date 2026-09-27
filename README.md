# CS 6220 — Data Mining Techniques

This repository holds all homework for **CS 6220: Data Mining Techniques** at Northeastern University.

**Author:** Tianyou

---

## Repository Structure

```
CS-6220-Assigment/
├── README.md            # This file
├── requirements.txt     # Pinned Python dependencies shared by all assignments
├── .gitignore
├── .venv/               # Local virtual environment (git-ignored, created during setup)
└── hw1/
    ├── homework_1.ipynb # HW1 notebook
    └── data/
        ├── iris.data    # UCI Iris dataset (CSV, no header row)
        └── iris.names   # Dataset description
```

Each assignment has its own `hwN/` folder with a notebook and a `data/` subfolder. New
assignments follow the same pattern (`hw2/`, `hw3/`, …).

---

## Environment

| Item | Value |
| --- | --- |
| Python | 3.9.6 |
| Editor / runner | VS Code with Jupyter notebooks |
| ML library | scikit-learn 1.6.1 |
| Data handling | pandas 2.3.3, NumPy 2.0.2 |
| Visualization | Matplotlib 3.9.4, seaborn 0.13.2 |
| Scientific computing | SciPy 1.13.1 |
| Platform | Local, MacBook (macOS) |

The full pinned dependency list is in [`requirements.txt`](requirements.txt).

---

## Setup

```bash
# 1. Clone
git clone https://github.com/Eeeeqyq/CS-6220-Assigment.git
cd CS-6220-Assigment

# 2. Create a virtual environment in the repo root
python3 -m venv .venv

# 3. Activate it (macOS / Linux)
source .venv/bin/activate
#    Windows (PowerShell)
#    .\.venv\Scripts\Activate.ps1

# 4. Install dependencies
pip install -r requirements.txt
```

5. Open the repo in VS Code, open a notebook, and choose the `.venv` interpreter
   (Python 3.9.6) from **Select Kernel** in the top-right corner.

> `.venv/` is git-ignored, so each machine builds its own. Activate it in every new terminal.

**Running notebooks:** each notebook loads data with a path relative to its own folder
(e.g. `data/iris.data`). Open and run it from inside its `hwN/` folder. VS Code does this
by default for notebooks. Use **Restart → Run All** to reproduce results from a clean state.

Notebook outputs are committed on purpose, so results can be read directly on GitHub.

---

## Assignments

### HW1 — Environment Setup and Iris Classification

**Folder:** [`hw1/`](hw1/) · **Notebook:** [`hw1/homework_1.ipynb`](hw1/homework_1.ipynb)

- Sets up the Python environment described above.
- Builds a scikit-learn `Pipeline` of `StandardScaler` + `LogisticRegression`.
- Uses an 80/20 stratified train/test split (`random_state=42`).
- Reports training and testing time, test accuracy, and a confusion matrix.
- Optional: sweeps the regularization parameter `C` over `[0.01, 0.1, 1, 10, 100]`.

**Data:** UCI Iris dataset in `hw1/data/iris.data`. The file has no header row. The notebook
names the columns and calls the label column `species`.

<!-- Template for new assignments:
### HWN — Title

**Folder:** [`hwN/`](hwN/) · **Notebook:** [`hwN/homework_N.ipynb`](hwN/homework_N.ipynb)

- Summary of tasks

**Data:** description and location
-->

---

## Data Policy

Small data files are committed so notebooks run as soon as the repo is cloned. Large datasets
are shared via OneDrive and are not committed. `.gitignore` ignores everything in
`hw*/data/` by default, and each committed data file has its own `!` exception line.

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `ModuleNotFoundError` | The notebook is on the wrong kernel, or the venv isn't active. Select the `.venv` kernel in VS Code. In a terminal, run `source .venv/bin/activate`. |
| `FileNotFoundError` for a data file | The notebook is running outside its `hwN/` folder. Open it from inside that folder so `data/...` resolves. |
| Broken environment | Rebuild it: `rm -rf .venv && python3 -m venv .venv && source .venv/bin/activate && pip install -r requirements.txt` |
| Added a new package | With the venv active, run `pip freeze > requirements.txt` and commit the result. |
