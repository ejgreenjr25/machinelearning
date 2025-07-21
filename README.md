# machinelearning

Abstract
Breast cancer is a leading cause of mortality globally, with survival duration influenced by various clinical and demographic features. This project aims to predict patient survival times using machine learning techniques applied to a dataset of breast cancer patients diagnosed with infiltrating ductal and lobular carcinoma. We have employed two regression models, Random Forest and Decision Tree with AdaBoost, enhanced with hyperparameter tuning and feature selection, to identify the most influential predictors. A key focus is evaluating the impact of including or excluding the feature ‘Status_Dead’, a binary variable indicating survival status, on model performance and interpretability. The model performs better with the inclusion of ‘Status_Dead’, while excluding it, shows that tumor size, age, and regional node information serve as significant predictors as well. These findings shine light on the value of machine learning in survival analysis while addressing the concerns of overreliance on certain variables and ensuring robust predictions.
Introduction
Breast cancer remains the most common cancer among women worldwide, with over 2 million new cases diagnosed annually. Despite advancements in detection and treatment strategies, survival rates still vary significantly due to factors such as disease stage, tumor size, patient age, and access to treatment. Predicting survival times can serve as a powerful tool for personalized medicine, enabling clinicians to tailor treatments, optimize resource allocation, and ultimately improve patient outcomes.
Machine learning has emerged as a transformative tool in healthcare, capable of uncovering hidden patterns within complex datasets and enhancing survival predictions. By training regression models on clinical and demographic data, we aim to identify key factors that influence survival time. However, challenges arise when certain features, such as ‘Status_Dead’ binary indicator of survival status), dominate predictions. This can lead to data leakage, inflating model performance but compromising interpretability. In this project, we apply Random Forest and AdaBoost machine learning models to predict breast cancer survival times. We explore two key questions:
1.	How effectively do machine learning models predict breast cancer patient survival times based on clinical and demographic features?
2.	What is the impact of including or excluding ‘Status_Dead’ on both model performance and the identification of influential predictors?
By comparing models trained with and without ‘Status_Dead’, we aim to highlight the role of alternative features such as tumor size, regional node involvement, and age, balancing predictive accuracy with clinical interpretability.
Hypothesis
Clinical and demographic characteristics such as tumor stage, patient age, and progesterone status will be good predictors of survival duration in breast cancer patients. By applying machine learning models to these factors, we will be able to estimate survival months with reasonable accuracy, which in turn will highlight key variables that have the most impact on survival times.
Methodology
To predict breast cancer survival times, we applied machine learning models using clinical and demographic data. Our approach included the following steps:
1.	Data Preprocessing
●	We used a dataset containing clinical and demographic information of breast cancer patients.
●	Categorical Variables were encoded using OneHotEncoder, transforming non-numerical data into binary features, ensuring compatibility with machine learning regression models.
●	Numerical Variables (Age, Tumor Size, etc.) were standardized using
StandardScaler to scale the features to a mean of 0 and a standard
deviation of 1, to improve model performance.
2.	Feature Selection
●	Mutual Information and Feature Importance techniques were applied to identify the most influential predictors of survival times
●	The inclusion and exclusion of ‘Status_Dead’ were explicitly tested in order to approximate its impact on model performance and feature rankings.
3.	Model Selection
●	We implemented two machine learning regression models:
-	Random Forest Regressor: A robust estimator that fits a number of decision tree regressors on various sub-samples of datasets, using averaging to improve the prediction accuracy.
-	AdaBoost Regressor: A boosting algorithm that iteratively improves weak learners, by focusing on errors from previous iterations.
4.	Hyperparameter Tuning
●	Hyperparameter tuning was performed using GridSearchCV with 5-fold Cross-Validation to identify the best parameters, such as the number of estimators, learning rate, and tree depth.
5.	Model Evaluation
●	We split the dataset into 80% training and 20% testing subsets, using train-test split.
●	Models were evaluated on the test set
Due to the continuous numerical nature of the target variable, survival months, regression models were used and compared with one another. Thus the metrics used to compare the two models were mean absolute error (MAE), mean squared error (MSE), and r-squared (R2).
6.	Feature Importance Analysis
●	Feature importance was visualized to identify which clinical and demographic features contributed most to survival predictions.
●	Comparisons were made between models with and without ‘Status_Dead’ to aid in understanding its influence on predictions.
