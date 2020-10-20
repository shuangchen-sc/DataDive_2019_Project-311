# DataDive 2019 : Project 311

In this one-day  “Hackathon" event organized by DataKind & Microsoft, I worked with a team of talented volunteers on a proof-of-concept product for the 311 service of US Cities to automatically categorize 311 complaints into relevant agencies/categories based on citizen-filed text fields.

## Motivation
PLACEHOLDER

## The Data
* The [NYC 311 Service Requests data](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/7ahn-ypff): Full dataset of NYC's 311 service requests covering a wide range of complaints citizens filed. The original data used for the DataDive is a subset for the timeframe of January 2018 - September 2019 (about 4.65 million rows; 41 columns. 2.59gb).
* The [San Francisco 311 Service Requests (July 2008 - October 2019)](https://data.sfgov.org/api/views/vw6y-z8j6/rows.csv?accessType=DOWNLOAD&bom=true&format=true): Supplementary data for another US city - San Fransisco
* The [Austin 311 Service Requests (March 2014 - October 2019)](https://data.austintexas.gov/api/views/i26j-ai4z/rows.csv?accessType=DOWNLOAD&bom=true&format=true): Supplementary data for another US city - Austin

## Approach
* I first performed EDA on the available text fields that can be used for classification and noted down the challenges with both the X (features) and Y (targets) of this classifcation tasks.
* I worked with the team to determine the scope for a proof-of-concept model to experiment for this 1-day event. I also helped create a longer term product vision and roadmap for future developments.
* I then experimented with traning a CNN model using the "Descriptor" field as the feature to predict the top 10 agencies in the NYC dataset (~931K records).
* Lastly, I applied the trained model on a test dataset of 600K records and evaluated the performance of the model. 

## Deliverables
* **Interactive Heatmaps**: PLACEHOLDER
* **Trend forecasts**: the SARIMA model predicted that: <br>
  - the "window", "solar", "hvac", "gas", "heat pump" & "furnace" categories are likely to increase  <br>
  - while "insulation", "boiler" & "heater" categories are likely to stay the same
* PLACEHOLDER
 
