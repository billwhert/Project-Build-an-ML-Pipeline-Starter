# Build an ML Pipeline for Short-Term Rental Prices in NYC

This project develops an end-to-end ML pipeline to predict short-term rental prices in New York City. The pipeline is designed for automation and reproducibility, retraining weekly as new data becomes available.

## Links

GitHub Repo (public): [Project-Build-an-ML-Pipeline-Starter](https://github.com/billwhert/Project-Build-an-ML-Pipeline-Starter)

W&B Project (public): [NYC Airbnb Tracking](https://wandb.ai/wwhite29-skip/nyc_airbnb?nw=nwuserwwhite29)

Final W&B Report: [NYC Airbnb ML Pipeline Report](https://wandb.ai/wwhite29-skip/nyc_airbnb/reports/New-York-City-Airbnb-ML-Pipeline-Report-V1-0-0-V1-0-1--VmlldzoxNDQ4Njg5OQ)

## Tools Used

- MLflow – Orchestrates the pipeline execution

- Weights & Biases (W&B) – Tracks experiments, metrics, and artifacts

- Hydra – Manages configurations

- Scikit-learn – Provides model training and evaluation

## Pipeline Structure

1) Download Data – Pulls raw data from W&B artifacts.
2) Basic Cleaning – Handles NaNs, converts types, removes outliers.
3) Data Checks – Validates schema and distributions.
4) Data Splits – Creates train/validation/test sets with stratification.
5) Model Training – Random Forest Regressor.
6) Model Testing – Evaluates performance on the held-out test set.

## Results

I evaluated multiple runs, reporting both the average performance and the best run:

### Validation:

- Average R² ≈ 0.56
- Average MAE ≈ 33.27
- Best run R² ≈ 0.57
- Best run MAE ≈ 32.42

### Test:

- Average R² ≈ 0.56
- Average MAE ≈ 33.85
- Best run R² ≈ 0.62
- Best run MAE ≈ 31.64

## Results/Summary:
The model explains between 56 to 62% of variance in NYC Airbnb prices. On average, predictions are off by about $32 to $33 per night, with best-case error around $31. Validation and test results were very close, indicating low overfitting and strong generalization.

## How to Run

1) Clone the repo and set up the environment:

"git clone https://github.com/billwhert/Project-Build-an-ML-Pipeline-Starter.git
cd Project-Build-an-ML-Pipeline-Starter
conda env create -f environment.yml
conda activate nyc_airbnb_dev"

2) Login to Weights & Biases:

wandb login [API_KEY]

3) Run the pipeline:

mlflow run .

## License

- [MIT License](LICENSE.txt)
