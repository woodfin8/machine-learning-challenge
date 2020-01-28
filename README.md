# machine-learning-challenge
Applying machine learning classification models to NASA's Kepler exo-planet dataset. 


## Table of contents

* [General info](#general-info)
* [Results](#results)
* [Technologies](#technologies)
* [Resources](#resources)

## General info
Random Forest and K-Nearest Neighbor classification models were trained and tested with the exo-planet data. There are three possible classes.
CONFIRMED: The object identified by the Kepler telescope is confirmed as an exo-planet
CANDIDATE: The object is a candiated for exo-planet designation
FALSE POSITIVE: An object of interest that has failed at least one exo-planet test.

Redundant and un-necessary columns were removed, leaving the following eleven features for the models 
'koi_fpflag_nt', 'koi_fpflag_ss', 'koi_fpflag_co', 'koi_fpflag_ec', 'koi_period', 'koi_impact', 'koi_duration', 'koi_depth', 'koi_prad', 'koi_teq', 'koi_model_snr'

Descriptions of features: https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html#pdisposition

The classes were turned to numerical values via 'LabelEncoder'. Feature data was scaled with 'MinMaxScaler' before running Random Forest and KNN models. 'GirdSearchCV' was then used to tune hyper-parameters of both models. 

Hyper-parameters selected befre and after-tuning with 'GridSearchCV'
Un-tuned Forest: n_estimators = 100
Tuned Forest: n_estimators = 200, max_depth = 50
Un-tuned KNN: n_neighbors = 5
Tuned KNN: n_neighbors = 21, weights = distance

## Results
|Model|Testing Data Score|
|---|---|
|Un-tuned Forest| 0.8987 |
|Un-tuned KNN| 0.8284 |
|Tuned Forest| 0.9016 |
|Tuned KNN| 0.8410 |

The Tuned Random Forest model had the highest accuracy when classifying the test data. This was a slight improvement over its Un-Tuned version (less than 3 one-thousandths of a percent). Both the versions of the KNN model had lower accuraciesthan the Un-Tuned Random Forest's.

## Technologies
* Jupyter notebook - version 4.1
* Python - version 3.7.3
* Pandas - version 0.23.4
* Sklearn - version 0.22.1

## Resources
https://www.kaggle.com/nasa/kepler-exoplanet-search-results
https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html#pdisposition
