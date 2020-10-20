# DataDive 2019 : Project 311

In this one-day  “Hackathon" event organized by DataKind & Microsoft, I worked with a team of talented volunteers on a proof-of-concept product for the 311 service of US Cities to automatically categorize 311 complaints into relevant agencies/categories based on citizen-filed text fields.

## Motivation
Several types of building infrastructure upgrades can lead to huge energy and value savings, e.g. installing solar panels, improving insulation or replacing boilers. 
If we can predict the type of improvements for different areas, we can use this information to inform policymakers or local communities to initiate changes. 

## The Data
* The [NYC 311 Service Requests data](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/7ahn-ypff): Full dataset of NYC's 311 service requests covering a wide range of complaints citizens filed. The original data used for the DataDive is a subset for the timeframe of January 2018 - September 2019 (about 4.65 million rows; 41 columns. 2.59gb).
* The [San Francisco 311 Service Requests (July 2008 - October 2019)](https://data.sfgov.org/api/views/vw6y-z8j6/rows.csv?accessType=DOWNLOAD&bom=true&format=true): Supplementary data for another US city - San Fransisco
* The [Chicago 311 Service Requests (July 2018 - October 2019)](https://data.cityofchicago.org/api/views/v6vf-nfxy/rows.csv?accessType=DOWNLOAD&bom=true&format=true): Supplementary data for another US city - Chicago

## Approach
* I first performed EDA on the available text fields that can be used for classification and noted down the challenges with both the X (features) and Y (targets) of this classifcation tasks.
* I worked with the team to determine the scope for a proof-of-concept model to experiment for this 1-day event. I also helped create a longer term product vision and roadmap for future developments.
* I then experimented with traning a CNN model using the "Descriptor" field as the feature to predict the top 10 agencies in the NYC dataset (~931K records).
* Lastly, I applied the trained model on a test dataset of 600K records and evaluated the performance of the model. 

## Deliverables
* **Interactive Heatmaps**: With the heatmaps, I can easily find zip codes with the most building work done, e.g., many solar works are done at the zipcodes 02131, 02136 & 02126. I can also zoom-in on the map to discover the exact location of smaller hotspot regions or blocks.
* **Trend forecasts**: the SARIMA model predicted that: <br>
  - the "window", "solar", "hvac", "gas", "heat pump" & "furnace" categories are likely to increase  <br>
  - while "insulation", "boiler" & "heater" categories are likely to stay the same
* There is **potential saturation** in the "solar" worktype at several zip codes: on average, one unit of property at several zip code locations have multiple works done over the years. This could indicate saturation of solar panels and is import for predicting which areas may have more solar opportunities.
 
