# Date: 10/08/2024
# Session 4: Data Modelling
-------------------------------------------------
# Topics: 	
	-Data Modelling
	-Types of Model
	-Model Building
	-Preprocessing in model
	-EDA in Model
	-Regression Model
	
	
# Learning Models:  Types:

### 1. Supervised Learning
	-Supervisers
	-Labelled
	-By proper guidance 
	-Explicit learning model (Classification/Regression)
	
    -Train an algorithm in a labelled data set to predict the correct output value for unseen data
    -Input / Output
    -Labelled data
    -Techniques: Classification and Regression (Prediction)
	
### 2. Unsupervised Learning
	-No supervisers
	-Not labelled
	-No guidance
	-It predicts the patterns
	
    -Train an algorithm to find similarities on abnormality in a dataset
    -Input
    -Unlabelled data
    -Techniques: Clustering, anomaly detection
    -Find patterns in data based on similarity

----------------------------
### 3. Semi-supervised learning
    -Supervised and Unsupervised techniques

----------------------------
### 4. Reinforncement Learning
    -Learning through trial and error method from interaction with an environment.
    -States and actions
    -No datasets required
    -Decision making techniques
    -Find actions that maximize rewards.

# Learning Model:
    ---------------
    Supervised Learning ----> Labelled data
    1. Classification: 
    	-Fraud detection
    	-Email spam detection
    	-Diagnostic (DSS)
    	-Image classification
    	
    2. Regression
    	-Risk assesment
    	-Profit prediction
    
    Unsupervised Learning ------> Unlabelled data
    1. Dimesion REduction
    	-Text mining
    	-Face Recognition
    	-Big data visualization
    	
    2. Clustering
    	-Biological appliaction
    	-Target marketting
    	-Market basket analysis
    
    
    Hybrid Model that include Supervised Learning -----  Labelled and Unlabelled data
    (Semi-supervised Learning)
  
# Terminologies:
--------------
    Model : specific representation learned from data by applying some machine learning algorithms.
    -A model is also called as a hypothesis.
    
    Feature: A feature is like a individual property of our data.
    
    Target(classifier/Label):It is a value predicted by our model.
    
    Training:The idea to give a set of inputs (features) and it's expected output(labels)
    
    Prediction:Once model is ready then it predicts the putput is called as prediction.


# Steps for development of application:
-------------------------------------
    1. Collect the data
    2. Preprocess the data
    3. Feature engineering 
    	-Feature transformation
    	-Feature encoding
    	-Feature scaling
    	-Feature selection
    	-Feature extraction
    4. Exploration of dataset (EDA)
    	-Analyze the data
    	-Apply the statistics to understand the data
    5. Split the data into Training and Testing dataset
    6. Apply learning algorithms on Training dataset
    7. Prediction model is ready to Testing data
    8. Model is ready for future prediction.


# Feature Engineering:
    -----------------------
    -It is the process of using domain knowledge to create features that make machine learning algorithm work more effectively.
    -It involves selecting, modifying or creating new features from raw data.
        
    Importance of feature engineering:
    ------------------------------------
    1. Improves Model performance:
    -Quality features can simplify the model and enhance the accuracy of models by providing relevant information.
    
    2. Reduces complexity:
    -Good features can simplify the model and reduce the risk of overfitting.
    
    3.Speed Up the training:
    -Effective features can reduce the computational resources required for model training.  

# Feature Engineering Techniques:
-------------------------------

### 1. Feature Selection:
    -It involves choosing a subset of relevant features for use in model construction.
    -Techniques involved :
    
    1.1 Filler method:
    -Statistical method to evaluate the relevance of feature.
    
    	-a. Chi-Square test: Measure the independence of two variables
    	
    	-b. Correlation coefficient:measurs the strength of the linear relationship between features
    
    1.2 Wrapper method:
    -It use a predictive model to evaluate feature subsets. 
    
    	-a. Recursive Feature Elimination(RFE): Iteratively removes the least important feature.
    	
    1.3 Embedded method:
    -used for features selection during the model training process. 
    	-a. Lasso regression: Add a penalty to the regression to shrink some coefficients to zero.
    

### 2. Feature Transformation:
    -It involves modifying or creating new features to improve the model's performance.
    
    2.1 Normalization: sclaes the features to standard range, typically [0,1]
    
    2.2 Standardization: scales features to have a mean of 0 and st dev of 1.

### 3. Encoding Categorical variable (text data)
    -It can be encoded into numerical format 
    
    3.1 One hot encoding: creates binary columns for each category
    
    3.2 Label encoding: assigning uniques integer values to each category

### 4. Feature Extraction:
    -It reduces the dimensionality of data while perseving important information. 
    -It also use to convert high dimensional data to low dimensional data.

  	-a. Principal Componenet Analysis (PCA): Transform features into a set of linearly uncorrelated components.


### 5. Feature Creation:
    -It involves generating new features from existing ones to capture additional information.

	-a.Polynomial features:create new features by computing polynomial combinations of the original features.
	
	-b.Interaction features:It captures the relationships between existing features.
