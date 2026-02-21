# FIFA-Player-Analysis
An end-to-end data science project exploring whether a player's height influences their finishing ability, using the FIFA player dataset with over 17,000 professional footballers.

## Research Question

> *Do shorter players tend to have higher finishing ability compared to taller players?*

This question was inspired by a well-known paradox in football: despite tall players having physical advantages like aerial dominance, many of the greatest finishers in history — Messi, Maradona, Neymar, Pelé — are notably short. This project uses data to investigate whether that pattern holds statistically.

## Project Structure

```
fifa-player-finishing-analysis/
│
├── FIFA_Study.ipynb       # Main analysis notebook
└── README.md
```

## Dataset

- **Source:** FIFA player dataset [Kaggle](https://www.kaggle.com/datasets/maso0dahmed/football-players-data)
- **Size:** 17,000+ professional football players registered with FIFA
- **Key Variables:**
  - **Independent:** `height_cm`
  - **Dependent:** `finishing`
  - **Confounders controlled for:** `age`, `overall_rating`, `positions`

## Methodology

The project follows the full data science lifecycle:

1. **Exploratory Data Analysis** — distributions, summary statistics, outlier detection
2. **Data Cleaning** — handling missing values, filtering irrelevant positions (e.g. goalkeepers)
3. **Visualization** — histograms, scatter plots, correlation heatmaps
4. **Feature Engineering** — scaling, selection, and confound control
5. **Machine Learning** — three regression models trained and evaluated

## Models & Results

| Model | R² | MAE | RMSE |
|---|---|---|---|
| Ridge Regression (+ Scaling) | 0.873 | 5.30 | 7.03 |
| Random Forest | **0.893** | **4.63** | **6.45** |
| XGBoost | 0.891 | 4.72 | 6.51 |

All three models generalized well with no evidence of overfitting.

## Key Findings

- **Height is not a strong predictor of finishing ability.** While it has a small positive coefficient in Ridge Regression (~0.30), it is far outweighed by technical attributes.
- **The top predictors of finishing** across all models were `positioning`, `volleys`, and `long_shots`.
- **Random Forest** achieved the best overall predictive performance (R² = 0.893).
- The results support the idea that finishing is a skill-driven ability, not a physical one — consistent with what we observe in real-world football.

## Ethical Considerations

- Model predictions should supplement, not replace, human judgment in player scouting.
- Players are more than their stats — context, coaching, and team dynamics are not captured in this dataset.
- Care should be taken not to reduce player evaluations to numerical scores alone.

## Tech Stack

- Python, Jupyter Notebook (Google Colab)
- pandas, numpy, matplotlib, seaborn
- scikit-learn (Ridge Regression, Random Forest)
- XGBoost

## 🚀 Getting Started

```bash
git clone https://github.com/YOUR_USERNAME/fifa-player-finishing-analysis.git
cd fifa-player-finishing-analysis
jupyter notebook FIFA_Study.ipynb
```

> Make sure you have the FIFA dataset available. You can find it on [Kaggle](https://www.kaggle.com/datasets/maso0dahmed/football-players-data) or similar sources.

## 👤 Author

Mohan Vamsi Varadaraju Priya
