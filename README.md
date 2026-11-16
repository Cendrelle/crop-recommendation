# Crop Recommendation Using Soil Measurements

## Project Overview

This project explores the use of machine learning to identify the most predictive soil characteristic for crop recommendation.

The objective is to determine which individual soil measurement — nitrogen (N), phosphorus (P), potassium (K), or pH — provides the best predictive performance when classifying crop types.

The project uses a multiclass classification approach based on Logistic Regression.

Completed as part of a DataCamp machine learning project.

## Business Problem

Farmers need to understand soil conditions to make informed crop selection decisions.

Since measuring every soil characteristic can be costly and time-consuming, this analysis investigates whether a single soil measurement can provide useful predictive information.

## Dataset

The project uses `soil_measures.csv`, containing:

| Feature | Description |
|---|---|
| N | Nitrogen content in the soil |
| P | Phosphorus content in the soil |
| K | Potassium content in the soil |
| pH | Soil pH value |
| crop | Target variable representing the recommended crop |

The dataset contains 22 crop categories.

## Tools and Libraries

- Python
- Pandas
- Scikit-learn

## Methodology

1. Load and inspect the dataset.
2. Separate the explanatory variables from the target variable.
3. Split the data into training (70%) and testing (30%) sets.
4. Train four independent multinomial Logistic Regression models, each using only one soil measurement.
5. Evaluate each model using the weighted F1-score.
6. Compare the results to identify the best-performing individual feature.

## Model Evaluation

The weighted F1-score was used to evaluate predictive performance across the 22 crop categories.

### Results

| Feature | Weighted F1-score |
|---|---:|
| Nitrogen (N) | 0.0956 |
| Phosphorus (P) | 0.1241 |
| Potassium (K) | 0.2347 |
| pH | 0.0679 |

### Key Finding

Potassium (K) achieved the highest weighted F1-score (0.2347) among the four individual soil measurements.

This suggests that potassium contains the strongest individual predictive signal for crop classification in this experiment.

However, this result does not establish that potassium alone is sufficient for reliable crop recommendations.

## Project Structure

```text
crop-recommendation/
├── README.md
├── notebook.ipynb
├── soil_measures.csv
├── requirements.txt
└── .gitignore
```

## How to Run

1. Clone this repository.
2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

3. Place `soil_measures.csv` in the `data/` directory.
4. Open the notebook and execute the cells.

## Limitations

- Each model uses only one soil measurement.
- The evaluation focuses on weighted F1-score.
- Feature selection and evaluation currently use the same test set.
- The analysis does not assess the combined predictive power of all four measurements.

## Acknowledgements

This project was completed as part of a DataCamp machine learning project.

