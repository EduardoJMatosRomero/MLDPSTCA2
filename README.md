# Data Survey Analysis

## Exploratory Data Analysis

There are 1470 entries in total, with 147 having missing values (1470-1323). There are 9 categorical columns and 26 numerical ones. The datatypes are floats and objects.

Columns to perform the study are “JobSatisfaction”,”PerformanceRating” and
“Attrition”.

### Statistical description of numerical columns

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture1.JPG)

• Age: Employees' ages vary moderately, averaging around 35.7 years.
• Daily Rate: Average £801.45, but with wide individual differences.
• Commute Distance: On average, employees live 8.06 km from work, with significant
variation.
• Education: Most employees have some college education (average level 2.7/5).
• Hourly Rate: Average £64.29, showing notable variation among employees.
• Job Level: Primarily lower to mid-level roles (average level 1.85).
• Work Experience: Employees average 9.7 years in total.
• Company Tenure: Average 5.7 years but ranges widely.
• Job Satisfaction: Varies widely from very dissatisfied to very satisfied.
• Performance Ratings: Less varied, mostly around the average.
• Data Distribution: Most numerical data follow a normal distribution.

### Statistical description of categorical columns

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture2.JPG)

• The profile of the average employee is the next one:
  BusinessTravel - Travel_Rarely
  Department - Research & Development
  EducationField - Life Sciences
  JobRole - Sales Executive
  OverTime - No
• The dataset is imbalanced, with certain categories occurring much more frequently than others.

## Data processing

### Labelling missing values

After the presence and distribution of null values were confirmed, NaNs in categorical features were labeled as a separate category.

Given the random distribution and low number of missing values, median imputation is being used via sklearn.impute's SimpleImputer. Outliers are not a concern since all data responses originate from a predefined question set.

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture3.JPG)

### Handling missing values in categorical features

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture4.JPG)

Multiple Imputation is used to handle numerical nulls while preserving data distribution, and to label nulls in categorical features for effective data preprocessing.

## Data Overview - Visual analysis

### Do overtime stresses employees and makes them have to leave?

![image](https://github.com/EduardoJMatosRomero/MLDPSTCA2/blob/main/Images/Capture5.JPG)
