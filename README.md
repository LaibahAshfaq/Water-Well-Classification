# Water Well Classification
![water well pic](https://github.com/LeebeeNYC/Phase-3-Project/assets/128645674/ae8b4f3e-4341-4c0c-900f-f2040306a0e7)
## Overview

Tanzania is currently going through a water crisis. Out of its population of 59 million people, 16 million people (28% of the population) lack access to safe water, and 44 million people (73%) lack access to safely managed household sanitation facilities(water.org, 2023). There are approximately 60, 000 water wells in the country; many require repair and are nonfunctional. Using the data from The Tanzania water ministry, our project aims to produce a machine-learning model that can accurately predict whether a well is functional or Non- Functional. 


## Business Understanding
The Stakeholders that would benefit from using a model to predict water well functionality are the UN's Water Aid Org, The Government of Tanzania and local non-profit groups. A model that would most benefit the population in need would have a low false negative rate, which means that the model doesn't predicts that it is functional when the well is nonfunctional. That would result in misclassification and the local population without water. 
We also want to minimize our false positive rates in order to prevent stakeholders from deploying mechanics to fix a perfectly functional well, which would be time costly. 

## Data Understanding
Our source for the dataset is Taarifa waterpoints dashboard, which aggregates data from the Tanzania Ministry of Water. We found this data from the DrivenData competition Pump It Up: Data Mining the Water Table (https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/page/23/).
From the original dataset we had 59, 400 entries and 41 features. After some strict EDA and a bit of feature engineering, we got 48, 651 entries and 12 features to work with.

### Features:
- basin: Geographic water basin
- region: Geographic location
- population: Population around the well
- construction_year: year well was constructed
- extraction_type_class: type of extraction used to make well
- payment_type: how was it paid for
- water_quality: quality of the well water
- quality_group: quality of the water
- quantity: quantity of well water
- source: source of water
- waterpoint_type: the kind of waterpoint
- status_group: if its functional (0) or nonfunctional (1)



## Exploratory Data Analysis
<img width="539" alt="Screen Shot 2023-06-23 at 6 10 06 AM" src="https://github.com/LeebeeNYC/Phase-3-Project/assets/128645674/6e43215c-a8e4-46de-b890-ba1c41fe1066">

<img width="548" alt="Screen Shot 2023-06-23 at 1 58 37 AM" src="https://github.com/LeebeeNYC/Phase-3-Project/assets/128645674/f74851d1-f6ac-4f86-8e64-d3c560467391">

<img width="544" alt="Screen Shot 2023-06-23 at 1 58 27 AM" src="https://github.com/LeebeeNYC/Phase-3-Project/assets/128645674/4747e359-5cfc-4e5d-a0f8-df02dfbec3f9">

Looked at the distribution of features across the two classes. 

## Modelling

Found the best model to be a K-n-neighbours model tuned to specific hyperparameters after conducting a grid search.

<img width="531" alt="Screen Shot 2023-06-23 at 2 00 10 AM" src="https://github.com/LeebeeNYC/Phase-3-Project/assets/128645674/5c75a1d9-06ff-4432-8f98-a91cb9701453">
<img width="388" alt="Screen Shot 2023-06-23 at 5 46 23 PM" src="https://github.com/LeebeeNYC/Phase-3-Project/assets/128645674/df9bedd8-ec0c-4f93-8557-4f5a8b65bd7a">
Summary Metrics: 
-  precision Score: 0.72
-  Recall Score: 0.77
-  f1 Score: 0.74
-  Cross-Validation Accuracy Scores 0.80
-  ROC = 0.88

<img width="385" alt="Screen Shot 2023-06-23 at 5 46 34 PM" src="https://github.com/LeebeeNYC/Phase-3-Project/assets/128645674/e85b0018-d585-4136-ad7a-a501b8808d45">

Our most important features for this model were found using permutation importance, which used the recall score to evaluate if each feature is important or not if it was removed from the model and how much its absence decreased the score. 
## Evaluation

This model did considerably better than the other ones, based on the recall score. Our first priority is to minimize false negative errors, thus our recall score is what we optimized for and we sacrificed having a barely higher f1 score for a greater recall. 

## Recommendations

Some recommendations for next step include looking at the most important features and prioritizing them. 
1 . The quantity of water was the feature of most importance and so we should look at how it affects functionality and if it leads to a well becoming more dysfunctional or functional. 
2. Water quality should also be used to test if the water is drinkable or not. More quantitative data on the water quality such as salt and fluoride content can help us determine how drinkable certain water wells and their sources are. 
3. Having water wells close to nearby villages and having more data on how spread out these wells are from them to analyze how accessible these wells are. The nearer a well is, the better life outcomes for the people, specifically women who are disproportionately affected by distant wells because they are the main group collecting water for their families. 

## Next Steps
1. To be able to use this model to predict how functional water wells are in other countries by proactively checking on wells that are predicted to be non-functional. 
