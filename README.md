# NLP Project — Emotion Classifier (Streamlit)

Simple Streamlit app that classifies the emotion conveyed in text using a scikit‑learn pipeline. The app displays the top prediction, confidence, and class probabilities, and tracks basic usage metrics in a local SQLite database.

## Features
- Emotion prediction with a pre‑trained scikit‑learn pipeline
- Probability chart via Altair; summary charts via Altair and Plotly
- Basic analytics: page visits and prediction logs (SQLite)
- Ready‑to‑run Streamlit UI

## Tech Stack
- `Python`, `scikit-learn`, `pandas`, `numpy`
- `streamlit`, `altair`, `plotly`
- `sqlite3` for lightweight persistence

## Quick Start
Prereqs: Python 3.9+ recommended.

1) Create and activate a virtual environment (optional but recommended):
   - macOS/Linux: `python3 -m venv .venv && source .venv/bin/activate`
   - Windows (PowerShell): `py -m venv .venv; .\.venv\Scripts\Activate.ps1`

2) Install dependencies:
   - `pip install -r app/requirements.txt`

3) Run the app from the repo root:
   - `streamlit run app/app.py`

The app will open in your browser. Use the sidebar to switch between Home, Monitor, and About.

## Usage
- Home: enter text, submit, and view predicted emotion, emoji, and confidence. A bar chart shows class probabilities.
- Monitor: view page visit logs and prediction history; includes bar and pie charts for quick summaries.
- About: brief project info.

## Project Structure
- `app/app.py`: Streamlit app entry point
- `app/models/emotion_classifier_pipe_lr_8_oct_2023.pkl`: pre‑trained classifier
- `app/track_utils.py`: SQLite helpers for logging
- `app/requirements.txt`: Python dependencies
- `data/emotion_dataset.csv`: sample dataset used for modeling
- `notebooks/`: notebook(s) and related artifacts
- `data.db`: SQLite database created at runtime (in the working directory)

Note on the database file: the app connects to `data.db` using a relative path. If you run `streamlit` from the repo root (recommended), `data.db` will be created/used in the root. Running from `app/` will create/use `app/data.db` instead.

## Model
The classifier is a logistic regression pipeline serialized with `joblib`. For experimentation or re‑training, see the notebook under `notebooks/`.

## License
MIT — see `LICENSE` for details.
