# Estimating and Predicting Extant Avian Mass using Ridge Regression

**Author:** John Adrian Ada  
**Date:** April 20, 2026

## Abstract
Accurate and precise mass estimates are important, both, for extinct and extant
organisms of the class Aves or Birds. While there have been many methods in
estimating the body mass of Birds from skeletal measurements, this model made
use of a Ridge Regression Model with K-fold cross validation to estimate and
predict the body mass of flying, extant Birds from 863 samples. All skeletal and
mass measurements were log-transformed to account for the non-linear relation
ships of the data and the expected collinearity was mitigated using the L2-ridge
penalty on an Ordinary Least Squares model with a 80-20 ratio for the train-test
split. Results found that the coracoid humorous-articulating facet (HAF) is the
best predictor of mass, with a 232.8130% change in mass for every one increase
in standard deviation, all else equal. The model had a mean squared error of
0.0197, a mean absolute error of 0.0092 and a mean absolute percentage error
of 2.15%. Overall, more samples are needed to create a more robust model,
which is limited to flying birds of similar size ranges to the samples. Different
methods are also needed to create a more robust model where new entries can
be introduced

## Dataset
The dataset utilized in this project is sourced from the **Vertebrate Zoology collection of the Yale Peabody Museum**.
* **Sample Size:** 863 samples of extant, flying birds.
* **Target Variable:** Mass (g)
* **Features:** Various skeletal measurements including:
  * Femur (circumference, diameter, length)
  * Humerus (circumference, diameter, length)
  * Tarsus (circumference, diameter, length)
  * Tibia (length)
  * Coracoid (HAF, shaft width, max length)

## Methodology
1. **Data Preprocessing:** All skeletal and mass measurements were log-transformed to account for the non-linear relationships inherent in the biological scaling data.
2. **Train-Test Split:** The dataset was split into an 80-20 ratio for training and testing the model.
3. **Model Selection:** Ordinary Least Squares (OLS) regression was explored initially. However, due to expected multicollinearity among the skeletal measurements, a **Ridge Regression model (L2 penalty)** was utilized to mitigate variance and improve generalizability. 

## Key Findings & Results
The Ridge Regression model proved highly effective at predicting avian mass with the following evaluation metrics:
* **Mean Squared Error (MSE):** 0.0197
* **Mean Absolute Error (MAE):** 0.0092
* **Mean Absolute Percentage Error (MAPE):** 2.15%

**Feature Importance:** The model identified the **coracoid humorous-articulating facet (HAF)** as the best predictor of avian body mass. Holding all else equal, there is a 232.8130% change in mass for every one standard deviation increase in the coracoid HAF measurement.

## Limitations & Future Work
* **Scope:** The current model is strictly limited to flying birds of similar size ranges to those present in the 863 samples. It may not generalize well to flightless birds (ratites) or birds with extreme mass outliers.
* **Future Work:** More samples are needed to create a more robust model. Furthermore, alternative non-linear modeling methods should be explored to create a system where new, out-of-distribution entries can be introduced accurately.

## Requirements
To run the Jupyter Notebook (`Bird-OLS.ipynb`), the following libraries are required:
* `numpy`
* `pandas`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `statsmodels`
