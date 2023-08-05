# Predicting Email Clicks

I particpated in an applied research project course taught by Professor Bill Franks and sponsored by IHG Hotel & Resorts. During this project I worked in a team of 4 with the goal ofe predicting whether a member would click an email or not. IHG and Kennesaw State University’s Data Science and Analytics department partnered this semester to provide graduate students with a use case for the DS7900 course in Spring semester of 2023. The data provided relates to IHG’s commercial email marketing operations, which IHG shared “aims to increase customers’ engagement and brand awareness”. The ultimate goals of these emails are to direct customers to create bookings, enroll in rewards offers or increase specific brand awareness.

### __Project Purpose__    
#### GOAL: The specific task posed by IHG was to accurately predict whether a member will click an email.  

The objectives to achieve the goal of accurately predicting include:

* Create a good understanding of the data provided
* Develop analytical plan
* Define parameters such as timeframe to be used for modeling cohort and history
* Feature engineer and feature select influential variables
* Properly merge the datasets into a singular data source for modeling
* Split data into appropriate training and testing datasets
* Build prediction models and train those
* Validate and understand performance of models
* Prepare presentation for IHG to communicate process, results, and recommendations

Leveraging predictive analytics to accurately forecast a customer's likelihood of clicking an email can significantly benefit IHG. By identifying optimal audiences for targeted campaigns, IHG will not only gain a deeper understanding of its member base but also boost the effectiveness of its marketing efforts. Consequently, this data-driven approach will contribute to the company's overarching goal of increasing product purchases and enhancing customer engagement.

### __Tools used__     
* Python  
* R  
* SQL

### __Results__    
The main results and recommendations found by this project are as follows:

1. The recency of a member’s click associates with a higher probability of a member clicking on another email.
2. An XGBoost model produces the highest Area Under the Curve (AUC: 95 %), lowest proportion of incorrectly identified members who would click (False Negatives: 0.2 %), and the highest proportion of correctly identified members who would click (True Positives: 1.6 %) when predicting whether a member would click an email.
3. If the cost of incorrectly identifying members who would not click is high, then a Naïve Bayes model, compared to the XGBoost model, produces a competitive proportion of True Positives (1.3 %) and False Negatives (0.5 %) while incorrectly identifying 5 % fewer members who would not click.

!["image"](https://github.com/njones738/Predicting-Email-Clicks/blob/main/data/images/executive_summary_images.jpg)

## Folder structure

```
- readme.md
- scripts
---- readme.md
---- 1. init_process.ipynb
---- 2. feature_engineering.ipynb
---- 3. data_sampling.ipynb
---- 4. model_work.ipynb
---- 5. testing.ipynb
---- 
- data
---- readme.md
---- images
---- 
- documents
---- readme.md
---- Final IHG Technical Report.doc
---- 
- deliverables
---- readme.md
---- Analytical Plan.pptx
---- Final Analysis Results.pptx
---- Initial Analysis Results.pptx
---- Final IHG Presentation.pptx
---- Final IHG Technical Report.pdf
---- 
```

## Deliverables

Overall, two deliverables were given by the end of the course:

1. Final Presentation to IHG
2. Technical Paper

During the course of the semester, three checkpoint deliverables were presented to Professor Franks and members of IHG's Advanced Analytics team:

1. Analytical Plan     
2. Initial Analysis Results     
3. Final Analysis Results     

## Data sources

The data for this project was provided by InterContinental Hotels Group (IHG). Three datasets were provided:

* Email History (192,134,300 observations & 8 variables):
    * Each observation represents a unique email sent to a member over time. The timespan of emails is between January 1st, 2020, and January 31st, 2022. This file contains the response variable for modeling – ‘CLICK’, as well as potential predictors of member click behavior. Three variables represent the unit of analysis: member, email campaign, and email send date. (See Table 1)
* Hotel Travel History (4,724,918 observations & 16 variables):
    * Each observation represents a unique room consumed by a member over time. This file contains potential predictors of member click behavior. Six variables represent the unit of analysis: member, hotel, hotel stay confirmation, date of stay confirmation, check-in date, and check-out date. (See Table 2)
* Member Information (1,233,429 observations & 11 variables):
    * Each observation represents a unique member. This file contains a snapshot of member demographic information as of collection date. (See Table 3)

Each file contains a consistent ‘HASH_NBR’ that represents a unique member which was used, alongside the time variables, to merge the datasets together. The Email History dataset contains the dependent variable ‘CLICK’ that will be used as the response variable in the model. Additional features were engineered from the variables in each of the three datasets. The process for the project includes many steps before and after building a model. Each of these processes will be discussed in turn.  
