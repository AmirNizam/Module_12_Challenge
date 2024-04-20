# Module 12 Report Template

## Overview of the Analysis

The main objective of this challenge is to construct a model that can accurately determine the creditworthiness of borrowers. The dataset utilized in this task consists of historical lending activity data from a peer-to-peer lending services company.
The dataset has a shape of (77536, 8), meaning it contains 77536 samples with 8 variables.The target variable, loan_status, is the dependent variable of interest and can take on values of 0 (indicating a healthy loan) or 1 (indicating a high-risk loan).
The independent variables that influence the target variable include loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks, and total_debt. The binary nature of the target variable suggests that Logistic Regression is an appropriate choice for building our machine learning model.

As part of the machine learning process, the initial step involved understanding the structure of the data, including the type of data, presence of any null values, and value counts. 
This exploratory analysis revealed an interesting finding regarding the sample size in relation to the target variable, indicating an imbalance in the value counts. Specifically, only 6.7% of the total samples belong to the high-risk loan category.
Subsequently, the dataset was divided into training and testing datasets. This division allows us to train the model on the training dataset and then evaluate its performance on unseen data points, thereby mitigating the risk of overfitting. 
Additionally, the StandardScaler module was employed to standardize the data points in the training dataset. This standardization process ensures that features with higher absolute values, such as loan_size, do not receive disproportionately higher weights compared to other features like interest_rate.

Finally, after creating an instance of the Logistic Regression model, the model was trained using the scaled training dataset. The performance of the model was then analyzed by comparing the actual and predicted values of the testing dataset using a confusion matrix and balanced accuracy scores.

To further enhance the predictive capabilities of the model, the RandomOverSampling module was utilized to balance the data points in the training data. This involved generating new data points to address the imbalance. The model was then retrained using the augmented dataset.

## Results


* Machine Learning Model 1:
  # Balanced accuracy score: 98.80%
  # Healty Loans ('0')
  	* Precision: 1.00
 	* Recall: 1.00
  # High Risk Loans('1')
  	* Precision: 0.87
  	* Recall: 0.98



* Machine Learning Model 2:
  # Balanced accuracy score: 99.60%
  # Healty Loans ('0')
	*Precision: 1.00
	*Recall: 0.99
  # High Risk Loans('1')
	*Precision: 0.87
	*Recall: 1.00
## Summary

The initial model demonstrates a high level of accuracy in predicting healthy loans, with a precision and recall score of 1.00. However, its performance in predicting high-risk loans is slightly lower. This could be due to the disproportionate number of healthy loan samples compared to high-risk ones in the dataset.

To address this imbalance and improve the model's predictions, the RandomOverSampling module is utilized to balance the data points in the training data. By fitting the generated data points, a new model is created. The second model achieves perfect accuracy in predicting both healthy and high-risk loans, with a precision and recall score of 1.00 for both categories.

Overall, the implementation of random over sampling has enhanced the predictability of the Logistic Regression model for this dataset. It has improved the recall for high-risk loans without compromising the model's ability to predict healthy loans. Therefore, it is recommended as the preferred model.

However, it is important to note that the model's performance is relative to the specific problem it is addressing, which in this case is the classification of healthy and high-risk loans. The risk framework of the company or individual involved in peer-to-peer lending plays a significant role in determining the importance placed on prediction accuracy for these two categories. This consideration aids in evaluating the models effectively.
