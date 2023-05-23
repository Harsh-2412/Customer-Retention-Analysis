#  Pwc Switzerland Power BI virtual case experience - Customer Retention Analysis

![Retention Dashboard](https://github.com/Harsh-2412/PWC_Customer_Retention_Analysis/assets/110857650/d8acd962-536d-45b4-9495-7cee329a0a49)



## Table of Contents
* Busines requirements 
* Tasks for Dashboard
* Data Sourcing
* Data Preparation
* Data Modeling
* Data Visualization
* Data Analysis
* Insights & Recommendations
* Shareable link

---
## Business Requirement: A dashboard about customer retention.

In addition, to better understand the data, the telecom Retention Manager has scheduled a meeting with 
the engagement partner at PwC to cover these points:

> * Customers in the telecom industry are hard-earned: we don’t want to lose them  
> * The retention department is here to get customers back in case of termination  
> * Currently, we get in touch after they have terminated the contract, but this is reactionary: it would be
> * better to know in advance who is at risk  
> * We have done customer analysis with Excel: it has always ended in a dead-end  
> * We would like to know more about our customers: visualised clearly so that it’s self-explanatory for
> our management


## Tasks For the dashboard -

> * Define proper KPIs
> * Create a dashboard for the retention manager reflecting the KPIs
> * Write a short email to him (the engagement partner) explaining your findings, and include suggestions
as to what needs to be changed

---

### Data Sourcing

The Dataset used for this project was presented by Pwc and available at:

[Customer Retention Dataset](https://github.com/Harsh-2412/PWC_CustomerRetentionAnalysis/blob/main/02%20Churn-Dataset.csv)

---

## Data Preparation 

> Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.
VArious Dax functions like **COUNT,COUNTROWS,FILTER, IF** etc Were used to create measues. 

The Customer retention dataset is given by a table named: CustomerTable 



----

## Data Modeling

After the dataset was cleaned and transformed, it was ready to be modeled(using Power BI Desktop).  
The fact and dimension have been combined into one table and is shown in the data model below

----

## Data Visualization

Data visualization for the dataset was done using Microsoft Power BI Desktop:

> * The Attrition Analysis (1/3) Page: Shows the Attrition 7 retention and various variables like Tenure period, Services offered and more that affect it.
> * The Customer analysis (2/3) Page: the Second Page visualizes Customer demographics along with variables that may affect Attrition like Age, Tenure PArtners, number of connections etc.
> * The Insights And recommendations(3/3) page: The Last Page provides the insights into Data after analysis.   
>  And Recommendations For the Firm to make decisions through this analysis of data.  

-----

## Data Analysis

# Measures Used in the Table

| Measure                   | Formula                                                                                               |
|---------------------------|-------------------------------------------------------------------------------------------------------|
| Total Customers           | `Countrows('CustomerTable')`                                                                          |
| Retention Rate            | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[Churn] = "No")), COUNTROWS('Customertable'))` |
| NoInternetServiceAttrition | `COUNTROWS(FILTER('CustomerTable','CustomerTable'[InternetService] = "No" && 'CustomerTable'[Churn] = "Yes"))` |
| InternetServiceAttrition   | `COUNTROWS(FILTER('CustomerTable','CustomerTable'[InternetService] <> "No" && 'CustomerTable'[Churn] = "Yes"))` |
| Attrition_BY_PS           | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[phoneservice] = "Yes" && 'CustomerTable'[Churn] = "Yes")), COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[Churn] = "Yes")))` |
| Attrition_By_TP           | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[DeviceProtection] = "Yes" && 'CustomerTable'[Churn] = "Yes")), COUNTROWS(FILTER('CustomerTable','CustomerTable'[Churn] = "Yes")))` |
| Attrition_By_ST           | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[StreamingTV] = "Yes" && 'CustomerTable'[Churn] = "yes")), COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[Churn] = "Yes")))` |
| Attrition_By_SM           | `DIVIDE(COUNTROWS(FILTER('CustomerTable','CustomerTable'[StreamingMovies] = "Yes" && 'CustomerTable'[Churn] = "Yes")), COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[Churn] = "Yes")))` |
| Attrition_BY_OS           | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[OnlineSecurity] = "Yes" && 'CustomerTable'[Churn] = "Yes")), COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[Churn] = "Yes")))` |
| Attrition_By_OB           | `DIVIDE(COUNTROWS(FILTER('CustomerTable','CustomerTable'[onlineBackup] = "Yes" && 'CustomerTable'[Churn] = "Yes")), COUNTROWS(FILTER('CustomerTable' ,'CustomerTable'[Churn] = "Yes")))` |
| Attrition_BY_IS           | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[InternetService] IN {"FiberOptic", "DSL"} && 'CustomerTable'[Churn] = "Yes")), COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[Churn] = "Yes")))` |
| Attrition_By_DP           | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[DeviceProtection] = "Yes" && 'CustomerTable'[Churn] = "Yes")), COUNTROWS(FILTER('CustomerTable','CustomerTable' [Churn] = "Yes")))` |
| Attrition Rate            | `DIVIDE(COUNTROWS(FILTER('CustomerTable', 'CustomerTable'[Churn] = "Yes")), COUNTROWS('Customertable'))` |
| AttritedCustomers         | `COUNTROWS(Filter('CustomerTable', 'CustomerTable'[Churn] = "Yes"))`                                  |


-----
### Insights & Recommendations 


#### Data Insights:

> * Overall attrition rate:   27% of customers attrited in the Analysis. Amounting to 1869 Customers
> * Short customer tenure:  47% of the attrited individuals had a customer tenure of less than 1 year.
> * Decrease in attrition:     After the first year, the attrition rate drops to 29%.
> * Monthly service users:   This group exhibited the highest rate of attrition at 43%.
> * Phone users:                   Among different services, phone users had the highest attrition rate.
> * Dependents' impact:      People with dependents were less likely to attrite, possibly due to the responsibility of supporting
                                          multiple individuals.

#### Recommendations: 

> * Improve customer onboarding:
Since customers with shorter tenure have a higher attrition rate, focus on providing a seamless and positive onboarding experience. This could include clear communication, personalized support, and guidance to help new customers understand the value of the services. 

> * Enhance monthly service offerings:
Given the high attrition rate among monthly service users, consider introducing additional features, benefits, or incentives to increase customer satisfaction and loyalty. 

> * Strengthen phone service:
 As phone users had the highest attrition rate, it is crucial to analyze the reasons behind their dissatisfaction or disengagement. 

> * Engage with dependents:
 Recognize the importance of customers with dependents and engage them effectively. Offer family plans or discounted rates for multiple users.
 
 ------
## Shareable Link to the Dashboard 


[Customer Retention Analysis](https://app.powerbi.com/view?r=eyJrIjoiOTIxNzU3YzUtZDZhYS00NGNlLTllZTktMTZlOGI3NDMyYmUwIiwidCI6ImE2Y2E4Mzc0LTgwOWUtNGYwYi05Mzg2LTkzN2E0YjQ0NmEwYiIsImMiOjEwfQ%3D%3D)
 
 
 

                                                                  









