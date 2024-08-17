# Date: 17/08/2024
# Session 4: Data Modelling
-------------------------------------------------
### Topics: 	

	-Regression Model
	-Linear Regression
	-Logistic Regression
	-Decision Tree Classifier
	-Random Forest Classifier
	
### Modelling: 
    -Supervised model
    -Unsupervised model
    	-semi-supervised model
    -Reinforcemnt model

# Modelling process:
--------------------
    1. Identify the problem:
    	-understand the problem and define the objectives of the model.
    2.Data collection:
    	-Collect relevant data for the model.
    3.Data preparation:
    	-Check and format the data to make it suitable for modelling.
    	-Steps are involved:
    		-Data Cleaning
    		-Data transform
    		-Exploratory Data Analysis (EDA)
    		-Splitting of the data in training and testing
    4.Model selection:
    	-choose the appropriate algorithm for the problem.
    5.Model Building and Training:
    	-Build the model and apply hypertuning or optimization
    6.Model Evaluation:
    	-Evaluate the trained model on the test dataset to determine its accuracy and performace.
    	-Techniques:
    		-Classification Report
    		-F1 score
    		-Precision
    		-Recall
    		-ROC curve
    		-Mean squared error
    		-Absolute error
    7.Model Tuning:
    	-Based on evaluation results, tune or optimize the model to improve the performance 
    8.Deployment of the model:
    	-Deploy the trained and tuned model in a production environment
    9.Monitoring and Maintenance:


# Model types:
----------------
### 1. Regression Model
	1.Linear Regression
![image](https://github.com/user-attachments/assets/6df4cd4e-93c5-4a69-9864-882d460ef2fd)

	-------------------
	2. Multi linear REgression 
	3. Polynomial Regression
	4. popular)Lasso Regression (
	5. Ridge Regression
	6. Elasticnet Regression
	
	The equation for line: y=mx+c
		m=slope of line =3
		c= constant (y-intercept) =5
		X=2
		
		y = mx + C
		  =3*2 + 5 = 11
		  
		X= Independent variable
		y= Dependent variable
![image](https://github.com/user-attachments/assets/987bc3a1-e763-41c0-89c9-e9d9a5f581c9)
	
### 2. Classification Model
### 3. Unsupervised Model : Clustering


### Regression: 
    DEfn:
    	-Statistical method to model the relationship between 2 variable called as dependent variable and independent variable.
    Purpose: 
    	-To unsderstand how the dependent variable changes corresponding independent variable.
    Key feature of REgression:
    	-It helps to find correlation between variables to predict continuous outcomes.
    Applications:
    	-Prediction applications
    	-Forecasting application
    	-Time series modelling
    	-Determining cause-effect relationship
	
### Terminologies:
	Dependent variable:Target variable to be predicted
	Independent cariable:Predictor affecting the dependent variable
	Outliers:Extreme values tha t can skew the results
	Multicollinearity:High coorelation among independent varaibles
	Underfitting:Poor model performance on training data
	Overfitting:Model performs well on training data but poorly on test data.
![image](https://github.com/user-attachments/assets/d938b91e-a4fa-450c-9fee-42371f4bb873)

### Linear Regression:
    -Statistical regression method used for predictive analysis.
    -Simple and easy algorithm demostrating relationship between continuous variables 
    -Shows the relationship between independent (X-axis) and dependent(y-axis) variables.
    -Type: 
    	-Simple linear regressio (SLR) 
    Equation: 
    y= aX + b
    
    y = Dependent variable
    X = Independent variable
    a = Slope (linear coefficient)
    b = Intercept

### Splitting of dataset in training data ans testing data:
![image](https://github.com/user-attachments/assets/19f3764c-f316-41ac-ade4-39ecd9963e4c)

