---
title: "Customer Churn Prediction"
header:
  teaser: "assets/images/churn-prediction.jpg"
categories:
  - Machine Learning
  - Classification
  - Clustering
tags:
  - Churn 
  - CNN
  - Prediction
  - K-Mean

author_profile: true
---

{% capture fig_img %}
![Foo]({{ '/assets/images/churn-prediction.jpg' | relative_url }})
{% endcapture %}

{{ fig_img | markdownify | remove: "
" | remove: "
" }}

### Proposal
This project aims to solve the churn problem for the banking domain. For any organization or company, customer churn is a major issue. A customer leaving for another product, subscription, or service is a loss for a company. Due to the direct impact on revenue, businesses need to classify customers who are likely to churn and might leave their services in near future. Apart from just recognizing the customers, they also need to identify the reason for churn, to offer them personalized perks. With the help of data mining and machine learning, we can predict the customers at the risk of churning. I am planning to perform two deliverables in this project. First, to predict bank customers likely to churn with the help of supervised learning and customer segmentation using unsupervised learning. There can be many factors causing customer churn, internal and external. In this project, I will try to find the probable reason for churning with the available data.
<br />

### Research Questions? Benefits? Why analyzes these data?
It is common among many organizations to focus more on attracting new customers rather than retaining the current ones. It could take a serious toll on the company’s revenue and overall profit margins. As per the mixpanel blog post [3], 97% of customers churn silently without providing any explanation. It is tough for a company to keep up with customer churn and make a profit at the same time. The lifetime value of the customer is measured by the total net income of the company from the customer over his lifetime.[6] With churn analysis, we can measure each customer’s value and cost to retain them.  There are many benefits of churn analysis:
 - Increase customer retention.
 - Increase profit margins.
 - Reduce customer attainment expense.
 - Improvement in customer service quality.
 - Lower marketing cost.
<br />


### Data
The source of bank data is Kaggle. This dataset contains details of a bank's customers and the target variable is a binary variable reflecting the fact whether the customer left the bank (closed his account) or he/she continues to be a customer. The dataset contains 10,000 records with 14 columns. There are no missing values. Demographically the information is about customers from Spain, France, and Germany. 55% of customers are Male, and 45% are Female, with an average age of 38.9 years. Exited is the outcome (churn) variable. 
The churn dataset contains below columns - 

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 10000 entries, 0 to 9999
Data columns (total 14 columns):
 #   Column           Non-Null Count  Dtype  
---  ------           --------------  -----  
 0   RowNumber        10000 non-null  int64  
 1   CustomerId       10000 non-null  int64  
 2   Surname          10000 non-null  object 
 3   CreditScore      10000 non-null  int64  
 4   Geography        10000 non-null  object 
 5   Gender           10000 non-null  object 
 6   Age              10000 non-null  int64  
 7   Tenure           10000 non-null  int64  
 8   Balance          10000 non-null  float64
 9   NumOfProducts    10000 non-null  int64  
 10  HasCrCard        10000 non-null  int64  
 11  IsActiveMember   10000 non-null  int64  
 12  EstimatedSalary  10000 non-null  float64
 13  Exited           10000 non-null  int64  
dtypes: float64(2), int64(9), object(3)
<br />

### Conclusion
In the financial and commercial world, machine learning has gotten extensive interest due to its capability of converting raw customer data into useful information. These efforts can easily fail short due to customer churning. So, it is important to focus on customers identified by the churn model. Bank and other financial institutions can greatly benefit from churn analysis. With this research, I will be trying to do customer churn prediction using data mining techniques and gain useful insights from customer’s raw information. 

### [Github Repository](https://github.com/GARV3007/Customer-Churn-Prediction){: .btn .btn--primary .btn--small}
