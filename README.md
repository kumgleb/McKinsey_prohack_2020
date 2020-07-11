# McKinsey & Company prohack 2020

Repository contains an updated version of my solution of the competition task. <br>
I took 62nd place out of 872 competitors with the submitted solution. <br>
Competition website: https://prohack.org/

## Task description:
The task consisted of two parts:
1. Predicting target values of `well being index` for countries in specific years using tabular data provided by organizers.
2. Allocating available resources according to predicted values so as to maximize potential for the growth of `well being index`.

Provided data was partly anonymized, names of countries and years were replaced by some arbitrary `galaxies` and `galactic years`. <br>
I suppose that it was done in order to prevent data leakage, as participants can find specific information about countries in open sources. <br>
Organizers provided formula to calculate `potential for increase in index` and `likelihood for index increase`. <br> 
`likelihood for index increase` depends on `potential for increase in index` and `energy`. which is the way the organizers called resources to be allocated. There were also few constraints on `energy` allocation in optimisation task. <br>
Solution scoring was based on a combined scaled metric: <br>

  80% prediction task RMSE + 20% optimization task RMSE * lambda, where lambda is a normalizing factor

## Short solution description:
As a result of EDA I ended up with a validation strategy and few strategies for tackling this problem. Then I chose two most time-efficient and optimal approaches. <br>
The first approach was to perform a generalized additive model based on  the time component. The second was to use the cleaned dataset with engineering features for gradient boosting model. Then I performed simple ensembling of those models using weighted sum of predictions. <br>
For optimisation task I applied probabilistic approach in order to take into account potential errors in `well being index`. <br>
All parts of the solution are divided in separate notebooks:
1. EDA (basic data analysis and formulation of solution and validation strategies)
2. Data cleaning and feature generation (dealing with missing values, preprocessing and feature generation)
3. Models (LinearGAM and CatBoost models, ensembling)
4. Optimisation task

 
