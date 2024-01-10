# Data Survey Analysis

## Exploratory Data Analysis

There are 1470 entries in total, with 147 having missing values (1470-1323). There are 9 categorical columns and 26 numerical ones. The datatypes are floats and objects.

Columns to perform the study are “JobSatisfaction”,”PerformanceRating” and
“Attrition”.

### Statistical description of numerical columns

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture1.JPG)

- Age: Employees' ages vary moderately, averaging around 35.7 years.
- Daily Rate: Average £801.45, but with wide individual differences.
- Commute Distance: On average, employees live 8.06 km from work, with significant variation.
- Education: Most employees have some college education (average level 2.7/5).
- Hourly Rate: Average £64.29, showing notable variation among employees.
- Job Level: Primarily lower to mid-level roles (average level 1.85).
- Work Experience: Employees average 9.7 years in total.
- Company Tenure: Average 5.7 years but ranges widely.
- Job Satisfaction: Varies widely from very dissatisfied to very satisfied.
- Performance Ratings: Less varied, mostly around the average.
- Data Distribution: Most numerical data follow a normal distribution.

### Statistical description of categorical columns

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture2.JPG)

The profile of the average employee is the next one:
- BusinessTravel - Travel_Rarely
- Department - Research & Development
- EducationField - Life Sciences
- JobRole - Sales Executive
- OverTime - No
The dataset is imbalanced, with certain categories occurring much more frequently than others.

## Data processing

### Labelling missing values

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture3.JPG)

After the presence and distribution of null values were confirmed, NaNs in categorical features were labeled as a separate category.

Given the random distribution and low number of missing values, median imputation is being used via sklearn.impute's SimpleImputer. Outliers are not a concern since all data responses originate from a predefined question set.

### Handling missing values in categorical features

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture4.JPG)

Multiple Imputation is used to handle numerical nulls while preserving data distribution, and to label nulls in categorical features for effective data preprocessing.

## Data Overview - Visual analysis

Do overtime stresses employees and makes them have to leave?

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture5.JPG)

A considerable number of employees left the company without working overtime, suggesting that overtime may not have a direct impact on the decision to leave.

### Is salary one of the main reasons?

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture6.JPG)

Most employees who leave the company have average incomes, which reduces the importance of the correlation between attrition and monthly income.

### What is the distribution of departments?

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture7.JPG)

The department with more employees is Research & Development.

### How does work experience affect attrition?

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture8.JPG)

### Employees typically leave the company within the first 10 years.

# Statistics Analysis

## Statistics Analysis (I)

### Correlation - Years In Current Role

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture9.JPG)

Employees who have worked under the same manager for a long time and have been in stable roles often receive more promotions and are less likely to leave. However, spending an extended period in the same position can lead to complacency, despite the benefits of job security and long-term company tenure.

***This situation highlights the need for further analysis and potential investment in enhanced career development opportunities to prevent stagnation and encourage continuous professional growth within the company.***

### Correlation - Years With Current Manager

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture10.JPG)

Employee tenure with the same manager and role duration correlate with promotion frequency, indicating that career growth is tied to managerial stability.

***The company should focus on implementing structured career development strategies beyond manager-employee relationships to provide more professional advancement opportunities.***

### Correlation - JobRole - Sales Executive

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture11.JPG)

Sales executives in the hierarchy experience job stability and higher income. However, there is a disconnect with core company sectors. Integrating sales roles into career plans could foster interdepartmental growth.

***Structured career development strategies should extend beyond manager-employee dynamics to enhance professional advancement.***

## Statistics Analysis (II)

### T-test

#### T-test | Age – Attrition

Hypothesis:

Null Hypothesis (H0): There is no significant difference in the average age of employees between the two attrition groups.
Alternative Hypothesis (H1): There is a significant difference in the average age of employees between the two attrition groups.

T-Statistic for Age: -3.3514082845782953, P-Value: 0.0008267367692839238

Given the low P-Value, we reject the null hypothesis (H0) which stated there is no significant difference in the average age of employees between the two attrition groups.

The negative T-Statistic value (-3.35) indicates that the average age of employees who have left the company ('Yes' to attrition) is lower than that of the employees who haven't left ('No' to attrition).

The P-Value of 0.00084 is significantly less than the common alpha level of 0.05. This low PValue indicates that the observed difference in ages between the two groups is statistically significant.

***Possible solutions:***
  ***- Career Development Opportunities.***
  ***- Recognition and Feedback.***
  
#### T-test | Training time last year – Attrition

Hypothesis:

Null hypothesis (H0): There is no significant difference in the amount of training received by employees who left and those who stayed.

Alternative hypothesis (H1): There is a significant difference in the amount of training received in the last year between employees who left and those who stayed.

T-Statistic for Distance: -2.134648835520212, P-Value: 0.03297332495134566

The t-statistic's negative value indicates that, on average, employees who left the company had fewer training sessions in the last year than those who stayed.

The p-value is slightly less than the typical alpha level of 0.05, suggesting that the result is statistically significant, albeit close to the threshold.

***This could indicate that training opportunities, or lack thereof, are a factor in employee retention. Employees who receive more training may feel more engaged, valued, and equipped to perform their roles, thereby reducing their likelihood of leaving.***

## Insights and Recommendations Summary Based on the Analysis

***Employees who remain in the same role for an extended period of time tend to have longer company service and managerial relationships. However, they may experience delays in promotion, which could indicate potential complacency. This highlights the need for enhanced career development initiatives.***
***In the sales hierarchy, job level is positively correlated with stability and income, unlike in the technical, manufacturing, and healthcare sectors. Integrating sales into career plans could bridge departmental gaps and increase growth opportunities.***
***Employees who work under the same manager for an extended period may experience professional stagnation.***
***Younger employees tend to have higher attrition rates, which may be due to fewer training opportunities. Therefore, increasing training could improve retention and job satisfaction.***

# Machine Learning algorithms

As it was analysed previously:
- The majority of numerical features demonstrate a normal distribution, with data concentrated around the mean.
- The dataset is imbalanced, with certain categories occurring much more frequently than others in categorical features.
***The purpose of our machine learning classification model is to predict whether or not employees are likely to leave the company.***

## Data Pre-processing  

- To address data imbalance, resampling techniques like SMOTE are used, generating synthetic samples for the minority class to enhance model performance.
- Certain non-determinant features like 'EducationField' and 'DistanceFromHome' are removed for better model focus.
- Binary labels like attrition and multi-level categories are not normalized due to class imbalance concerns.
- One-Hot Encoding is applied for categorical variables, suitable for nominal data.
- The chosen machine learning models are Random Forest, Gradient Boosting, and Decision Tree, suitable for mixed data types.
- To mitigate overfitting, a validation strategy like cross-validation is employed, ensuring reliable model performance assessment on unseen data.
- Entries with missing attrition responses are removed.

## 70-30 % Data split

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture12.JPG)

Gradient Boosting Model:
- The Gradient Boosting Model is effective in predicting the "No" class but struggles significantly with the "Yes" class, both in terms of precision and recall.
Decision Tree Model:
- The Decision Tree Model shows a more balanced performance between the two classes than Gradient Boosting, though it still struggles with the "Yes" class. The model is more consistent across precision and recall for each class.
Random Forest Model:
***- The Random Forest Model shows the highest accuracy and is very effective in predicting the "No" class but has a significant issue with the "Yes" class, missing the vast majority of actual "Yes" instances.***

### Cross Validation 70-30 % - Random Forest

***[0.69 - 0.91333333 - 0.92 - 0.95317726 - 0.94983278]***

The accuracy of the model varies significantly, ranging from 69% to 95%. This suggests that the model's performance is sensitive to data splits and potential data peculiarities. High scores in certain folds raise concerns about overfitting, particularly if they exceed domain knowledge expectations or previous performance benchmarks.

## Hyperparameter Tuning 70-30 % (I)

### Adjusting Class Weights in Random Forest - Automatic Balancing

Using Random Forest, it possible to adjust the class weights to give more importance to the
"No" class. This can help the model pay more attention to the minority class.

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture13.JPG)

The model accurately predicts the 'No' class but struggles with the 'Yes' class due to the imbalanced dataset. The high accuracy is misleading as the model shows a strong bias towards the 'No' class, as evidenced by the high recall and F1-score for 'No' and very low recall and F1-score for 'Yes'.

### Cross Validation 70-30 % - Random Forest Hyperparameter tunned- Class Weight adjusted with Automatic Balancing

***[0.69 - 0.91333333 - 0.92 - 0.94983278 - 0.94314381]***

The Random Forest model exhibits varying accuracy across folds, ranging from 0.69 to 0.9498, indicating performance dependence on data subsets. With the exception of the first fold, accuracies exceed 90%, indicating overall effectiveness. The model's final analysis considers the complexity of capturing voluntary attrition factors.
