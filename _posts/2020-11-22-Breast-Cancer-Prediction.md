---
title: "Breast Cancer Prediction"
header:
  teaser: "assets/images/breast-cancer-pink-ribbon.jpg"
categories:
  - Classification
tags:
  - Random Forest
  - Logistic Regression
  - sklearn
toc: true
author_profile: true
---

{% capture fig_img %}
![Foo]({{ '/assets/images/breast-cancer-pink-ribbon.jpg' | relative_url }})
{% endcapture %}

{{ fig_img | markdownify | remove: "
" | remove: "
" }}

### Abstract
Breast cancer or breast carcinoma is uncontrolled growth of epithelial cells in the breast. The uncontrollable division of one cell results in visible mass named tumor. Tumor can be benign or malignant. By Johns Hopkins Pathology, benign tumors are non-malignant/non-cancerous tumor and malignant tumors are cancerous growths. A cancer is another word for a malignant tumor. Most benign tumors respond well to treatment. But, malignant tumors are often resistant to treatment, may spread to other parts of the body and they sometimes recur after they were removed. Under a study by University of Wisconsin, 569 patients (212 with cancer and 357 with benign masses) provided the data for diagnostic algorithm. Diagnostic features are computed from a digitized image of a fine needle aspirate (FNA) of a breast mass. They describe characteristics of the cell nuclei present in the image in the 3-dimensional space is that described in: [K. P. Bennett and O. L. Mangasarian: "Robust Linear Programming Discrimination of Two Linearly Inseparable Sets", Optimization Methods and Software 1, 1992, 23-34]. Breast cancer is the most common malignancy in women, with over 200,000 being diagnosed in the US every year. 40,000 women will die from it each year. The objective of this research is to provide a comparative study on the utilized potential classification tools (Linear regression, random forest) on the problem by a benchmark dataset which consist of numeric cellular shape features extracted from preprocessed Fine Needle Aspiration biopsy image of cell slides.
 
 <br />

### Problem Statement
Breast Cancer is the 2nd most common cancer in women. But, on rare scenario can also happen to men. It is 2nd leading cause of deaths of women after lung cancer. A fine needle biopsy is an effective tool in evaluating and diagnosing suspect lumps or masses. With early diagnosis of breast cancer, patients can be isolated for early treatment for a better chance of survival. Common biopsies for breast cancer diagnosis includes fine-needle aspiration (FNA), core needle biopsy, and MRI-guided biopsy.  In this analysis, we will be using ten features of tumour cell nuclei extracted from the digital image processing of an FNA of a breast mass to predict breast cancer. The data is collected from UCI Machine learning repository.
 
 <br />

### Data
The benchmark dataset in this research will obtained from the UCI Irvine machine learning repository http://archive.ics.uci.edu/ml/index.html. This dataset was originally created by Dr. Wolberg, Street and Mangasarian all from University of Wisconsin. Data items in the dataset are composed of ID number, the diagnosis which will either be classified as malignant (M) or benign(B) and numeric shape features of extract cellular nuclei such as radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, and symmetry and fractal dimension. Each of the dataset in the observation is composed of 30 variables and 10 of the featured variables are related to the aforementioned characteristics. As described in the website, following main features were computed for each cell nucleus and will be used as input for our analysis. All feature values are recoded with four significant digits.
1.	radius (mean of distances from center to points on the perimeter)
2.	Texture (standard deviation of gray-scale values)
3.	Perimeter
4.	Area
5.	Smoothness (local variation in radius lengths)
6.	Compactness (perimeter^2 / area - 1.0)
7.	Concavity (severity of concave portions of the contour)
8.	Concave points (number of concave portions of the contour)
9.	Symmetry
10.	Fractal dimension ("coastline approximation" - 1)
 
 <br />

### Methodology
Our aim is to build a classification model that will identify breast cancer using diagnosis label. For this purpose, we are planning to use logistic regression classifier, Random Forest classifier. Logistic Regression classifier will establish the baseline training results and we will compare that with results from Random Forest.<br />
Logistic regression (LR) is a statistical method similar to linear regression since LR finds an equation that predicts an outcome for a binary variable, Y, from one or more response variables, X. However, unlike linear regression the response variables can be categorical or continuous, as the model does not strictly require continuous data. To predict group membership, LR uses the log odds ratio rather than probabilities and an iterative maximum likelihood method rather than a least square to fit the final model. This means the researcher has more freedom when using LR and the method may be more appropriate for nonnormally distributed data or when the samples have unequal covariance matrices. Logistic regression assumes independence among variables, which is not always met in morphoscopic datasets. However, as is often the case, the applicability of the method (and how well it works, e.g., the classification error) often trumps statistical assumptions.

<br />

### Results
We used sklearn’s GridSearchCV to fine tune the parameters for above model and then compared the results. We have created Pipelines for Random Forest and Logistic Regression model with different parameters. Then we passed different values through these pipeline parameters to GridSearchCV for module tuning. We have used seeding for reproducibility.
Random Forest classifier are not best suited for skewed class distribution. Our dataset is imbalanced dataset. But it is not heavily imbalanced (cancer: no-cancer as 1:2). So, we decided that we don’t need calibration.<br />
Based on the accuracy we selected the best parameters for Random Forest and Logistic Regression classifier. Also based on the accuracy, we have selected Random Forest as our best model. We have then tested both of these models using our test dataset and calculated accuracy and f1-score. f1-score is a harmonic mean of precision-recall. We have also produced confusion matrix for each test.<br />

### [Github Repository](https://github.com/GARV3007/Predictive-Analytics-Project){: .btn .btn--primary .btn--small}

### References
<https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29> <br />
<https://www.kaggle.com/uciml/breast-cancer-wisconsin-data>