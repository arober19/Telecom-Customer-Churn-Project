Project Brief

Problem Statement:
This Telecom company wants to determine which customers will likely unsubscribe as it costs approximately 5 times more money to acquire new customers rather than to keep existing ones. In order to keep the existing customers, they must first find out which customers are at risk of leaving. Unfortunately, they do not know how to evaluate this. This may result in substantial monthly profit losses that could otherwise be resolved.

By performing an analysis on the current and past customer data to discover which variables contribute to the churn of customers, counter-measures can be applied to ensure the retention of the clients.

Current State:
The data being worked with is a data frame of 7043 current and past customers including information across 21 columns such as tenure, type of subscription, monthly charges, payment method, contract type and churn etc....

Data Preparation:
To start, the dataset provided was already adequately clean. There were no null or  nan values and no duplicates. Next, to create all the input variables certain categorical columns needed to be converted to dummy variables in order to be evaluated. This included all columns save for monthly charges, total charges and tenure as those values contained continuous data. With the data-frame all set up because of the discrepancy between the categorical data being zeroes and ones and the continuous data not, the continuous data must be scaled. Additionally, because the target variable or the churn had much more values of 0 rather than 1, the 1 values(customers that did leave) had to be up-sampled while training the model. This was accomplished by using the resample method in python. 

Modelling:
Following that, a train test split was applied to the dataset and several models were tested on the data such as: logistic regression, random forest, decision tree classifier, linear support vector machine as well as the Naïve-Bayes model. Each model was favored best on its recall score because the high cost of this dataset were False Negative Classifications, meaning if a customer was predicted not to leave the company but in actuality they did. The model which produced the highest recall score with maintaining a legitimate accuracy was the logistic regression model. With an accuracy of 0.74 and a recall of 0.81. Of course each of these models required tuning based on their C, solver and penalty values.

After applying the model, the features with the highest contribution to churn turned out to be: the monthly charges, month-to-month contracts, fiber optic service, as well as electronic cheques as a payment method. The features with the highest contribution to no churn were: tenure, total charges, tech support, and two year contracts. All of these variables make sense as they have to do with building relationships between the company and the client, the less commitment which is produced as a result of a specific feature the less likely the customer will stay with the company and vice-versa.

Performance:
After performing the freshly tuned, trained and tested model on the original data. This outputs a list of 1237 customers out of the 7043 which are at risk of leaving the company. This means that the model outputted a probability greater than 0.5 that is between 0 and 1 that the customer will leave. Based on this information, I sought out the result if all the customers on the list converted from the features most likely to contribute to churn to the features least likely to. This new output then produced a customer list of only 834 people, a 33 % reduction in the at-risk list already. Future work is required as to why fiber optic service contributed to customer churn as well as determining an optimal discount percentage on the monthly charges to keep customers while also still maximizing profit.

Output/Deliverable/Usage: 
List of At-Risk Customers as well as Recommendations on next-steps.

Stakeholders: 
Customer Experience Department

Due Date: June 26th 2019

Measures of Success:
The success of this project will be determined by how effective the recommendations as a result of my analysis perform in their implementation. This would be based on how many customers actually leave the company over time and how much profit is maintained. 

Summary:
Can recover up to 37.5% of total potential losses
Emphasize one or two year contracts to clients & Encourage bank transfers as a payment method
The goal is to strengthen the company - customer relationship.

Future Work:
Apply survival analysis to determine how much longer a customer will stay and how much more value they add to the company
Look into optimal discount percentages that maximize profit



