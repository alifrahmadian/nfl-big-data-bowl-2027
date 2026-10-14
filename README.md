# NFL Big Data Bowl 2027 — Combine-to-Game Analysis

An independent entry for the **Open Track** of the [NFL Big Data Bowl 2027](https://www.kaggle.com/competitions/nfl-big-data-bowl-2027).

The project investigates whether movement characteristics measured during NFL Scouting Combine drills provide useful information about regular-season NFL performance.

**Current status:** repository setup and an initial exploratory notebook. No competition data has been analyzed yet; the research question, metrics, and results are still to be determined.

## Start locally

Python **3.12** is the recommended starting environment for this project.

From the project directory, check your Python version and create an isolated environment:

```bash
python3 --version
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

If `python3` points to another version and you already have Python 3.12 installed, use `python3.12 -m venv .venv` instead.

Open `notebooks/01_data_exploration.ipynb` in VS Code and select `.venv/bin/python` as its kernel. Install the Microsoft Python and Jupyter extensions if needed. Alternatively:

```bash
jupyter lab
```

The notebook also runs without downloaded data and explains what to do next.

## Get the data

1. Join the competition and accept its rules on Kaggle.
2. Download the competition data from the **Data** tab.
3. Extract the files into `data/raw/`; nested directories are supported.
4. Run the notebook from the first cell. Review the file inventory and set `SELECTED_FILE` if you want to inspect a particular CSV.

Competition data is deliberately excluded from Git. Keep it local and use the official competition page as the access point. Keep API tokens and other credentials out of the repository.

## Repository contents

| Path | Purpose |
| --- | --- |
| `notebooks/01_data_exploration.ipynb` | File inventory, bounded CSV sample, schema, missing values, and initial questions |
| `data/raw/` | Original competition files; ignored by Git |
| `data/processed/` | Derived datasets; ignored by Git |
| `reports/figures/` | Selected figures for the writeup and portfolio |
| `reports/research_notes.md` | Research decisions, assumptions, and experiment log |
| `requirements.txt` | Initial Python dependencies |
| `.gitignore` | Excludes environments, datasets, notebook checkpoints, and secrets |

## Development workflow

1. Inspect the schema, units, identifiers, and data coverage.
2. Understand how Combine records link to regular-season records.
3. Choose one position group and a narrow, testable research question.
4. Define a baseline and assess whether tracking features add useful information.
5. Validate claims with appropriate player/cohort separation and football context.
6. Record results, limitations, and reproducible steps.

The initial notebook reads **at most 50,000 CSV rows**. Its diagnostics describe that sample, not the full dataset. Change the limit only when needed; avoid loading all tracking files into memory at once.

This starter intentionally leaves dependencies unpinned. After installation in your project environment, record the versions used for your experiments:

```bash
python -m pip freeze > requirements-lock.txt
```

Commit that file after the environment works. Use `python -m pip install -r requirements-lock.txt` when reproducing those experiments in a fresh environment.

## Git and GitHub

Initialize the repository on your laptop after extracting this starter:

```bash
git init -b main
git add .
git status --short
git commit -m "Initialize NFL Big Data Bowl 2027 project"
```

If Git asks for an author name or email, configure your own identity; a GitHub-provided noreply email is an option.

Create an empty GitHub repository named `nfl-big-data-bowl-2027` without an additional README, license, or `.gitignore`. Then replace `YOUR_USERNAME` below with your GitHub username:

```bash
git remote add origin https://github.com/YOUR_USERNAME/nfl-big-data-bowl-2027.git
git push -u origin main
```

The starter archive contains no Git history, downloaded datasets, credentials, or virtual environment. Create these locally as appropriate.

## Kaggle submission

The competition requires a writeup and an attached **public Kaggle Notebook**. The published limits are 2,000 words and fewer than 10 tables/figures. Review the current rules and evaluation requirements before submitting.

Develop locally, and periodically run the notebook on Kaggle to check portability. This initial notebook can discover CSV files under `/kaggle/input` when running on Kaggle. Notebook compatibility alone does not make it a valid final entry: it still needs a completed analysis and writeup.

## Results

No results yet. This section will be updated with the final research question, baseline comparison, findings, and limitations after analysis.

## References

- [Competition overview](https://www.kaggle.com/competitions/nfl-big-data-bowl-2027/overview)
- [Competition data](https://www.kaggle.com/competitions/nfl-big-data-bowl-2027/data)
- [Competition rules](https://www.kaggle.com/competitions/nfl-big-data-bowl-2027/rules)
- [NFL Combine](https://operations.nfl.com/calendar-events/nfl-combine/nfl-scouting-combine)
- [NFL tracking data and Next Gen Stats](https://operations.nfl.com/game-operations-logistics/technology/performance-tracking-data-next-gen-stats)

This project is not affiliated with or endorsed by the NFL, AWS, or Kaggle.
