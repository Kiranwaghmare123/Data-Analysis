### **Titanic Case Study**

The Titanic dataset is one of the most widely used datasets in the field of data science and machine learning. It contains information about passengers who were aboard the Titanic, such as their demographics, ticket class, and whether they survived the shipwreck. This case study will walk through a series of tasks involving data exploration, cleaning, and modeling using Python, with the goal of predicting the survival of passengers based on available features.

---

### **Dataset Description**
The dataset consists of the following key columns:

1. **PassengerId**: Unique identifier for each passenger.
2. **Survived**: Binary outcome (0 = Did not survive, 1 = Survived).
3. **Pclass**: Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd).
4. **Name**: Name of the passenger.
5. **Sex**: Gender (male, female).
6. **Age**: Age in years.
7. **SibSp**: Number of siblings or spouses aboard the Titanic.
8. **Parch**: Number of parents or children aboard the Titanic.
9. **Ticket**: Ticket number.
10. **Fare**: Fare paid by the passenger.
11. **Cabin**: Cabin number (if available).
12. **Embarked**: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton).

---

### **1. Data Loading and Exploration**

#### **Question 1: How do we load the Titanic dataset and examine its basic structure?**

**Answer**: We will use the Pandas library to load and explore the dataset. Here’s how to load the dataset and get a basic understanding of the data.

```python
import pandas as pd

# Load the dataset
titanic_data = pd.read_csv('titanic.csv')

# Display the first few rows of the dataset
print(titanic_data.head())

# Check for missing values and basic statistics
print(titanic_data.info())
print(titanic_data.describe())
```

---

### **2. Data Cleaning**

#### **Question 2: How do we handle missing values in the dataset, especially for the 'Age' and 'Cabin' columns?**

**Answer**: The 'Age' column contains missing values, and the 'Cabin' column has many missing values. We'll fill the missing ages with the median age of the passengers and drop the 'Cabin' column for simplicity, since it has too many missing entries.

```python
# Fill missing values in the 'Age' column with the median value
titanic_data['Age'].fillna(titanic_data['Age'].median(), inplace=True)

# Drop the 'Cabin' column due to excessive missing data
titanic_data.drop(columns=['Cabin'], inplace=True)

# Check for any remaining missing values
print(titanic_data.isnull().sum())

# Fill missing values in 'Embarked' with the most common port
titanic_data['Embarked'].fillna(titanic_data['Embarked'].mode()[0], inplace=True)
```

---

### **3. Exploratory Data Analysis (EDA)**

#### **Question 3: What are the survival rates by gender and class? Visualize these relationships.**

**Answer**: We’ll analyze the survival rates by gender and class using groupby and visualization libraries like Matplotlib and Seaborn.

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Survival rates by gender
print(titanic_data.groupby('Sex')['Survived'].mean())

# Survival rates by class
print(titanic_data.groupby('Pclass')['Survived'].mean())

# Visualization: Survival by gender
sns.barplot(x='Sex', y='Survived', data=titanic_data)
plt.title('Survival Rates by Gender')
plt.show()

# Visualization: Survival by class
sns.barplot(x='Pclass', y='Survived', data=titanic_data)
plt.title('Survival Rates by Class')
plt.show()
```

- **Observation**: Women had a much higher survival rate than men, and passengers in 1st class had a higher survival rate than those in 2nd and 3rd class.

---

### **4. Feature Engineering**

#### **Question 4: How can we create a new feature representing the family size of a passenger?**

**Answer**: We can create a new feature `FamilySize` by summing the `SibSp` and `Parch` columns, which represent the number of siblings/spouses and parents/children aboard.

```python
# Create a new feature 'FamilySize'
titanic_data['FamilySize'] = titanic_data['SibSp'] + titanic_data['Parch'] + 1

# Display the first few rows with the new feature
print(titanic_data[['SibSp', 'Parch', 'FamilySize']].head())

# Visualize survival rates by FamilySize
sns.barplot(x='FamilySize', y='Survived', data=titanic_data)
plt.title('Survival Rates by Family Size')
plt.show()
```

---

### **5. Model Building**

#### **Question 5: How do we build a machine learning model to predict survival?**

**Answer**: We will use Scikit-Learn to build a Random Forest classifier to predict the survival of passengers. Before training the model, we will encode categorical variables (`Sex` and `Embarked`) and split the dataset into training and testing sets.

```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, roc_auc_score

# Encode categorical variables
titanic_data['Sex'] = titanic_data['Sex'].map({'male': 0, 'female': 1})
titanic_data = pd.get_dummies(titanic_data, columns=['Embarked'], drop_first=True)

# Define feature columns and target variable
features = ['Pclass', 'Sex', 'Age', 'Fare', 'FamilySize', 'Embarked_Q', 'Embarked_S']
X = titanic_data[features]
y = titanic_data['Survived']

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Build a Random Forest Classifier
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
rf_model.fit(X_train, y_train)

# Make predictions
y_pred = rf_model.predict(X_test)

# Evaluate the model
accuracy = accuracy_score(y_test, y_pred)
conf_matrix = confusion_matrix(y_test, y_pred)
roc_auc = roc_auc_score(y_test, rf_model.predict_proba(X_test)[:, 1])

print(f'Accuracy: {accuracy}')
print(f'Confusion Matrix: \n{conf_matrix}')
print(f'ROC-AUC Score: {roc_auc}')
```

---

### **6. Model Evaluation**

#### **Question 6: How do we evaluate the model's performance?**

**Answer**: We evaluate the model using the following metrics:

1. **Accuracy**: The percentage of correct predictions.
2. **Confusion Matrix**: Shows the breakdown of true positives, true negatives, false positives, and false negatives.
3. **ROC-AUC Score**: Measures the area under the ROC curve and indicates how well the model separates classes.

---

### **7. Conclusion**

In this case study, we explored and cleaned the Titanic dataset, performed exploratory data analysis, created new features, and built a machine learning model to predict passenger survival. The Random Forest model provided decent accuracy and a good ROC-AUC score. This process demonstrates the standard workflow of a data science project, from data preprocessing to model evaluation.

---

This completes the Titanic case study!
