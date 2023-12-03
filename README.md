## Capstone Project - AIML Course
```
This is the final project of the AIML course.
```
### Problem Statement
In this practical application, lets try to understand the lifestyle of people with diabetes/pre-diabetic/healthy. Look at the impact of major chronic conditions like Cholestrol, High Blood Pressure, Heart Disease etc. along with patient habits of eating/smoking and drinking alcohol

### Data Source
Link to Data Source: https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008 

### Data Description
There are 101766 rows and has 47 features and 1 target variable. The dataset has zero categorical columns and all are numeric columns. The dataset has 0 missing values. The dataset has 0 nan values.

### Data Preprocessing
Check for any missing values and remove the columns with more than 50% missing values. Check for any nan values and remove the columns with more than 50% nan values. Check for any duplicate rows and remove the duplicate rows. Check for any duplicate columns and remove the duplicate columns. Check for any constant columns and remove the constant columns. Check for any duplicate rows and remove the duplicate rows. Check for any duplicate columns and remove the duplicate columns. Check for any constant columns and remove the constant columns. Check for any duplicate rows and remove the duplicate rows. Check for any duplicate columns and remove the duplicate columns. Check for any constant columns and remove the constant columns. Check for any duplicate rows and remove the duplicate rows. Check for any duplicate columns and remove the duplicate columns. Check for any constant columns and remove the constant columns. Check for any duplicate rows and remove the duplicate rows. Check for any duplicate columns and remove the duplicate columns. Check for any constant columns and remove the constant columns. Check for any duplicate rows and remove the duplicate rows. Check for any duplicate columns and remove the duplicate columns. Check for any constant columns and remove the constant columns. Check for any duplicate rows and remove the duplicate rows. Check for any duplicate columns and remove the duplicate columns. Check for any constant columns and remove the constant columns.
Observed: Number of nan/missing values exist in the dataset is 0
Standard Scaling is applied to the dataset to scale the data.

### Exploratory Data Analysis
Heatmap of the correlation matrix of the complete dataset:
![all-heatmap.png](images%2Fall-heatmap.png)

Out of 47 features, following key features are selected for the analysis.
1. BMI -- Body Mass Index
2. HighBP -- High Blood Pressure (0 = no high BP 1 = high BP)
3. HighChol -- High Cholestrol (0 = no high cholesterol 1 = high cholesterol)
4. HeartDiseaseorAttack -- Heart Disease or Heart Attack
5. Smoker -- Smoker
6. HvyAlcoholConsump -- Heavy Alcohol Consumption
7. PhysActivity -- Physical Activity 
8. Diabetes_binary -- Target Variable (Diabetic/Pre-Diabetic/Healthy) (0 = no diabetes 1 = prediabetes or diabetes)

Heatmap of the correlation matrix of the selected features:

![heatmap-keyfeatures.png](images%2Fheatmap-keyfeatures.png)

### Model Building
Baseline Model: DummyClassifier makes predictions that ignore the input features.This classifier serves as a simple baseline to compare against other more complex classifiers. **The baseline model has an accuracy of 0.8606709239987386**

Following models are used to predict the target variable.
1. Logistic Regression
2. Decision Tree Classifier
3. K Neighbors Classifier
    Optimized the number of neighbors using GridSearchCV. The optimal number of neighbors is 16
    Mis-classification error for K nearest neighbor model with different values of K
    ![knn-misclassification-error.png](images%2Fknn-misclassification-error.png)
4. Support Vector Classifier
5. Random Forest Classifier

### Model Evaluation
                      Model     Fit_Time     Score  Max_Depth
0       Logistic Regression     0.122869  0.860415        0.0
1        K Nearest Neighbor    17.615237  0.860750        0.0
2  Decision Tree Classifier    18.542615  0.863199        7.0
3      SVM (Default Params)  2230.663658  0.862445        0.0

### Conclusion
```