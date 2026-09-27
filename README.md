# CS 6220 — Data Mining Techniques

Coursework repository for **CS 6220: Data Mining Techniques** at Northeastern University.

Each homework assignment is a self-contained Jupyter notebook (`homework_1.ipynb`,
`homework_2.ipynb`, …) together with any data files it depends on. Notebooks are committed
with their outputs intact, so the results can be read directly on GitHub.

**Author:** Tianyou

---

## Repository Structure

```
CS-6220-Assigment/
├── .gitignore           # Standard Python/Jupyter ignores; excludes .venv and .ipynb_checkpoints
├── README.md            # This file
├── requirements.txt     # Pinned Python dependencies for the whole course
├── .venv/               # Local virtual environment (git-ignored, created during setup)
├── data/                # Raw datasets used by the notebooks
│   └── iris.data        # UCI Iris dataset for HW1 (CSV, no header row)
└── homework_1.ipynb     # HW1 — one notebook per assignment
```

> **Note:** `.gitignore` and `requirements.txt` are present today. `data/` and the
> `homework_*.ipynb` notebooks are added as each assignment is completed, and `.venv/`
> is created locally by the setup steps below and never committed.

---

## Environment

| Item | Value |
| --- | --- |
| Python | 3.9.6 |
| Editor / IDE | JupyterLab 4.5.11 |
| ML library | scikit-learn 1.6.1 |
| Data handling | pandas 2.3.3, NumPy 2.0.2 |
| Visualization | Matplotlib 3.9.4, seaborn 0.13.2 |
| Scientific computing | SciPy 1.13.1 |
| Platform | Local laptop (macOS) |

The full pinned dependency list — including the JupyterLab and IPython kernel stack — is in
[`requirements.txt`](requirements.txt).

---

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/Eeeeqyq/CS-6220-Assigment.git
cd CS-6220-Assigment
```

### 2. Create a virtual environment

Create a virtual environment named `.venv` in the repository root:

```bash
python3 -m venv .venv
```

### 3. Activate it

**macOS / Linux:**

```bash
source .venv/bin/activate
```

**Windows (PowerShell):**

```powershell
.\.venv\Scripts\Activate.ps1
```

Once active, your prompt is prefixed with `(.venv)`.

> `.venv/` is listed in `.gitignore` and is **not** committed — each machine builds its own.
> The environment must be **activated in every new terminal session**; it does not persist
> between terminals.

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Launch JupyterLab

```bash
jupyter lab
```

This opens JupyterLab in your browser, rooted at the repository directory.

---

## Running a Notebook

1. Activate the virtual environment and start JupyterLab (steps 3 and 5 above).
2. Open the assignment notebook, e.g. `homework_1.ipynb`.
3. Confirm the kernel in the top-right corner is the `.venv` Python 3.9.6 interpreter.

To reproduce all results from a clean state, use **Kernel → Restart Kernel and Run All Cells…**
in the JupyterLab menu. This clears all in-memory state and re-executes every cell top to
bottom, so the committed outputs can be verified end to end.

Notebooks read their data using paths relative to the repository root (e.g. `data/iris.data`),
so launch JupyterLab from the repository root rather than from a subdirectory.

---



