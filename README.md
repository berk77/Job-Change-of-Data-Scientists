# HR Analytics: Job Change of Data Scientists

This dataset is designed to understand the factors that lead a person will work for the company(leaving a current job), and the goal of this task is to build a model that uses the current credentials, demographics, experience to predict the probability of a candidate looking for a new job or will work for the company.

## Data


* enrollee_id : Unique ID for candidate
* city: City code
* city_ development _index : Developement index of the city (scaled)
* gender: Gender of candidate
* relevent_experience: Relevant experience of candidate
* enrolled_university: Type of University course enrolled if any
* education_level: Education level of candidate
* major_discipline :Education major discipline of candidate
* experience: Candidate total experience in years
* company_size: No of employees in current employer's company
* company_type : Type of current employer
* lastnewjob: Difference in years between previous job and current job
* training_hours: training hours completed
* target: 0 – Not looking for job change, 1 – Looking for a job change

## Missing data

![](images/missing_values.png)

## Visual EDA

![](images/cities.png)

![](images/education_level.png)

## Preprocessing data

Since the education_level property is an ordinal category, I implemented an appropriate method for it. To make the difference between the categories more obvious, I increased the difference between them numerically. Likewise, in the company_size property, I created the categories by calculating the average values. Apart from these, I made some replacement operation and data type corrections.

In order to prevent data leakage, encoding categorical variable operations are done after data is separated as train and test data. First of all, the LeaveOneOutEncoder method was used here because the city variable is a high cardinality categorical variable. Then, the OneHotEncoder method was used, as variables such as gender, enrolled_university, major_discipline, company_type were nominal variables.

## Handling imbalanced dataset

I used the SMOTEENN method to solve the Imbalanced dataset issue. SMOTE can generate noisy samples by interpolating new points between marginal outliers and inliers. This issue can be solved by cleaning the space resulting from over-sampling. We can do this by using the SMOTEENN method.

## Result

![](images/features_importances.png)

In general, I tried to show what was done in the project. If you want to examine it in more detail, <a href = 'https://www.kaggle.com/gokberkyucelkaya/hr-analytics-job-change-of-data-scientists'>you can reach the notebook here.</a>
