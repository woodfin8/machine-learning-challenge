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

## Results
| |Testing Data Score|
|---|---|
|Forest| 0.8987 |
|KNN| 0.9016 |
|Tuned Forest| 0.8284 |
|Tuned KNN| 0.8410 |





## Technologies

### Languages Used

* Python

### Data Extraction, Cleaning and Reverse Geo-coding

* Jupyter notebook - version 4.1
* Python - version 3.7.3
* Pandas - version 0.23.4
* Numpy - version 1.15.4
* Glob 
* uszipcode - version 0.2.4 

### Data Rendering and Visualization

* Tableau Public - version 2019.4

## Resources
