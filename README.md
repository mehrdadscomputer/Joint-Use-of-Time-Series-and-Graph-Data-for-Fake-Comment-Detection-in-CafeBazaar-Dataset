# Fake Comment Detection in the CafeBazaar Dataset

This project contains the notebook used for the paper "Joint Use of Time Series and Graph Data for Fake Comment Detection in CafeBazaar Dataset". It builds app-level time-series features from review timing, rating deviation, and weekly review counts, then trains an LSTM autoencoder to learn what a normal review pattern looks like. Reviews with unusually high reconstruction error are treated as suspicious.

## Contents

- `fake_comment_detection.ipynb` — main analysis and model workflow
- `requirements.txt` — Python dependencies for running the notebook

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Data

Place the CafeBazaar review dataset in the same folder as the notebook, or update the notebook's `data_path` to match your local file location. The notebook checks for files such as:

- `review_details_v3`
- `review details.csv`

## Run

Open the notebook in Jupyter or VS Code:

```bash
jupyter notebook fake_comment_detection.ipynb
```

## Notes

This is a legacy research notebook that was cleaned up for readability in 2026 without altering the original logic. The workflow focuses on app-level sequence construction, anomaly detection, and exporting per-app time series for downstream use.

The output of this pipeline will be an input to the Rev2's implementation. You can find the code fo Rev2 here: https://cs.stanford.edu/~srijan/rev2/

