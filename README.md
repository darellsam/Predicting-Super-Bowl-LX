# Predicting Super Bowl LX

Basically, I was rooting for the Seahawks, the model picked the Seahawks... and hint hint, it was right haha.

This is an end-to-end NFL analytics project that combines historical game data, betting market signals, Elo ratings, and roster context to estimate win probabilities for Super Bowl LX.

## Why this project

I wanted to build a realistic sports prediction workflow that balances clean data engineering with practical modeling. This project focuses on one goal: estimate game outcomes as probabilities, not just binary picks.

## The fun part

The model called it right: the Seahawks won Super Bowl LX.

And yes, I was rooting for Seattle the whole time.

## Project structure

```text
data/
	raw/
		elo/
		nflverse/
		odds/
notebooks/
	00_data_setup.ipynb
	01_analysis.ipynb
```

## Workflow overview

1. Build and cache datasets from multiple sources (nflverse, Elo, odds).
2. Engineer game-level features, including:
	 - spread/total market signals
	 - Elo and Elo differential
	 - rolling team form
	 - QB continuity and depth-chart starter proxies
3. Train and evaluate models using time-based train/test splits.
4. Calibrate probabilities for better confidence estimates.
5. Simulate outcomes with Monte Carlo to produce win percentages and fair odds.

## Models used

- Logistic Regression (with imputation + scaling)
- HistGradientBoostingClassifier
- CalibratedClassifierCV (Platt scaling)

## Quick start

1. Create and activate a Python virtual environment.
2. Install required libraries used in the notebooks (pandas, numpy, matplotlib, scikit-learn, pyarrow, etc.).
3. Run `notebooks/00_data_setup.ipynb` to build local caches.
4. Run `notebooks/01_analysis.ipynb` for feature engineering, training, calibration, and simulation.

## Notes

- Raw data artifacts are ignored in Git to keep the repo lightweight.
- Notebook outputs may vary slightly if source data is refreshed.

---

Built for fun, rigor, and football.
