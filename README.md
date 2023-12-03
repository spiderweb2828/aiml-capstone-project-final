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

Count Plot of the target variable (Diabetes_binary):

![count plot.png](images%2Fcount%20plot.png)

Histogram of the target variable (Diabetes_binary):

![hist-output.png](images%2Fhist-output.png)

### Model Building
Baseline Model: DummyClassifier makes predictions that ignore the input features.This classifier serves as a simple baseline to compare against other more complex classifiers. **The baseline model has an accuracy of 0.8606709239987386**

Following models are used to predict the target variable.
1. Logistic Regression
    <br><br>Confusion Matrix for Logistic Regression model<br>
    ![Confusion Matrix for Logistic Regression model](images%2Fcm-lgr.png)
    
    <br>Classification report for Logistic Regression model
    
                          precision    recall  f1-score   support
        
                   0       0.87      0.99      0.92     43667
                   1       0.49      0.08      0.14      7069
        
            accuracy                           0.86     50736
           macro avg       0.68      0.53      0.53     50736
        weighted avg       0.82      0.86      0.81     50736

2. Decision Tree Classifier
    <br><br>Confusion Matrix for Decision Tree Classifier<br>
    ![cm-dt.png](images%2Fcm-dt.png)
    
    <br>Classification report for Decision Tree Classifier model<br>

                        precision    recall  f1-score   support
         
                    0       0.87      0.99      0.92     43667
                    1       0.50      0.09      0.15      7069
         
             accuracy                           0.86     50736
            macro avg       0.69      0.54      0.54     50736
         weighted avg       0.82      0.86      0.82     50736


3. K Nearest Neighbors Classifier

   Optimized the number of neighbors using GridSearchCV. The optimal number of neighbors is 16

   <br><br>Mis-classification error for K nearest neighbor model with different values of K<br>
   ![knn-misclassification-error.png](images%2Fknn-misclassification-error.png)

   <br><br>Confusion Matrix for KNN<br>
   ![cm-knn.png](images%2Fcm-knn.png)

   <br>Classification report for K Neighbors Classifier model<br>
              
                        precision    recall  f1-score   support
         
                    0       0.87      0.99      0.92     43667
                    1       0.50      0.09      0.15      7069
         
             accuracy                           0.86     50736
            macro avg       0.69      0.54      0.54     50736
         weighted avg       0.82      0.86      0.82     50736





4. Support Vector Classifier

   <br><br>Confusion Matrix for SVM<br>
   ![cm-svc.png](images%2Fcm-svc.png)
   
   <br>Classification report for Support Vector Classifier model<br>

                         precision    recall  f1-score   support
         
                    0       0.87      0.99      0.93     43667
                    1       0.57      0.05      0.09      7069
         
             accuracy                           0.86     50736
            macro avg       0.72      0.52      0.51     50736
         weighted avg       0.83      0.86      0.81     50736

    
                

5. Random Forest Classifier

   <br><br>Confusion Matrix for Randon Forest Classifier<br> 
   ![cm-rf.png](images%2Fcm-rf.png)

    <br>Classification report for Random Forest Classifier model<br>

                         precision    recall  f1-score   support
         
                    0       0.87      0.98      0.92     43667
                    1       0.49      0.09      0.15      7069
         
             accuracy                           0.86     50736
            macro avg       0.68      0.54      0.54     50736
         weighted avg       0.82      0.86      0.82     50736
    

6. Hyperparameter Tuning
   Used GridSearchCV to find the best hyperparameters for the model. Using GridSearchCV and K-neighbors classifier, we found that the optimal number of neighbors is 16. For decision tree classifier, we found that the optimal max_depth is 7. For SVM, we could not find the optimal kernel as there is not enough compute power and it is taking too much time to converge. so used the  SVM classifier is used with default inputs.

7. Model Evaluation
                            Model     Fit_Time     Score  Max_Depth
      0       Logistic Regression     0.122869  0.860415        0.0
      1        K Nearest Neighbor    17.615237  0.860750        0.0
      2  Decision Tree Classifier    18.542615  0.863199        7.0
      3      SVM (Default Params)  2230.663658  0.862445        0.0
      4  Random Forest Classifier     0.460712  0.860178        0.0


8. Conclusion
   The baseline model has an accuracy of 0.8606709239987386 and compared to the baseline model, the following models have better accuracy.
    1. K Nearest Neighbor
    2. Decision Tree Classifier
    3. SVM (Default Params)
    4. Random Forest Classifier
   
Overall, Decision Tree Classifier has the best accuracy of 0.863199 and the best fit time of 18.542615 seconds. So, Decision Tree Classifier is the best model for this dataset.

```