# DataDive 2019 : Project 311

In this one-day  “Hackathon" event organized by DataKind & Microsoft, I worked with a team of talented volunteers on a proof-of-concept product for the 311 service of US Cities to automatically categorize 311 complaints into relevant agencies/categories based on citizen-filed text fields.

## Motivation
311 complaints or service requests can be on different issues that need to be addressed by the relevant city agencies. Some cities may have a ticketing systems for the citizens to select relevant agencies, but citizens may not always know which agency is directly responsible for their issues. Take NYC for example, there are around 30 agencies with a lot more sub-divisions responsible for different types of issues. The good news is that citizens almost always provide a free-text description of the issues and an ML/NLP model that automatically classify requests to the applicable agencies will help shorten the time from request initiation to resolution. 

## The Data
* The [NYC 311 Service Requests data](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/7ahn-ypff): Full dataset of NYC's 311 service requests covering a wide range of complaints citizens filed. The original data used for the DataDive is a subset for the timeframe of January 2018 - September 2019 (about 4.65 million rows; 41 columns. 2.59gb).
* The [San Francisco 311 Service Requests (July 2008 - October 2019)](https://data.sfgov.org/api/views/vw6y-z8j6/rows.csv?accessType=DOWNLOAD&bom=true&format=true): Supplementary data for another US city - San Fransisco
* The [Austin 311 Service Requests (March 2014 - October 2019)](https://data.austintexas.gov/api/views/i26j-ai4z/rows.csv?accessType=DOWNLOAD&bom=true&format=true): Supplementary data for another US city - Austin

## Approach
* I first performed EDA on the available text fields that can be used for classification and noted down the challenges with both the X (features) and Y (targets) of this classifcation tasks.
* I worked with the team to determine the scope of a proof-of-concept model to test out for this 1-day event. I also helped create a longer term product vision and roadmap for future developments.
* I then experimented with traning a CNN model using the "Descriptor" field as the feature to predict the top 10 agencies in the NYC dataset (~931K records).
* Lastly, I applied the trained model on a test dataset of 600K records and evaluated the performance of the model. 

## Deliverables
* **EDA Notebook**: The data profile of each field in the example NYC 311 dataset. Analysis that shows the "Agency" field is more suitable to use as the target for the MVP while "Agency Name" field would require more effort in cleaning before it can be used to train a classifier. Another insight is that some complaint types are specific to a particular agencies and not all complaint types would have sufficient number of records to train a deep learning model.
* **A MVP CNN Model**: The trained multi-class classification CNN model made very precise prediction on 9 out of the 10 target labels, but its performance on recalls varied widely across the classes.The large sample size of HPD (New York City Department of Housing Preservation and Development) in the training set seems to have biased the model to classify more items in the test set to HPD and casued the high recall and low precision of this particular class. It is also worth noting that the "descriptor" field seems like a pre-set selections of strings dependent on complaint types highly correlate with different agencies. In a case where an end-user can enter free text and 311 would like to generate/auto-populate/suggest labels such as agencies/complaint types, a deep learning model can become more advantageos as the descriptions become less predictable and complex.
