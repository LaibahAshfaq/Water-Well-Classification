# Phase-3-Project
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
- status_group: if its functional or non functional



## Explain your stakeholder audience and dataset choice here
## Modeling
## Evaluation
## Conclusion
