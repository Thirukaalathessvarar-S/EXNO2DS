# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING
```
Developed by : Thirukaalathessvarar S
Reg no : 212222230161
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

dt = pd.read_csv("/content/titanic_dataset.csv")

dt.info()

# DISPLAY NO OF ROWS AND COLUMNS
print("Number of Rows and Columns:", dt.shape)

# SET PASSENGER ID AS INDEX COLUMN
dt.set_index('PassengerId', inplace=True)

dt.describe()

"""**CATEGORICAL DATA ANALYSIS**"""

# USE VALUE COUNT FUNCTION AND PERFORM CATEGORICAL ANALYSIS
categorical_columns = ['Survived', 'Pclass', 'Sex', 'SibSp', 'Parch', 'Embarked']
for column in categorical_columns:
    print("Value counts for", column, ":\n", dt[column].value_counts(), "\n")

"""**UNIVARIATE ANALYSIS**"""

# USE COUNTPLOT AND PERFORM UNIVARIATE ANALYSIS FOR THE "SURVIVED" COLUMN IN TITANIC DATASET
plt.figure(figsize=(8, 5))
sns.countplot(x='Survived', data=dt)
plt.title('Survival Count')
plt.show()

# IDENTIFY UNIQUE VALUES IN "PASSENGER CLASS" COLUMN
print("Unique values in Passenger Class column:", dt['Pclass'].unique())

# RENAMING COLUMN
dt.rename(columns={'Sex': 'Gender'}, inplace=True)
dt

"""**BIVARIATE ANALYSIS**"""

# USE CATPLOT METHOD FOR BIVARIATE ANALYSIS
plt.figure(figsize=(8, 5))
sns.catplot(x='Survived', hue='Pclass', kind='count', data=dt)
plt.title('Survival Count by Passenger Class')
plt.show()

# USE BOXPLOT METHOD TO ANALYZE AGE AND SURVIVED COLUMN
plt.figure(figsize=(8, 5))
sns.boxplot(x='Survived', y='Age', data=dt)
plt.title('Age Distribution by Survival Status')
plt.show()

"""**MULTIVARIATE ANALYSIS**"""

# USE BOXPLOT METHOD AND ANALYZE THREE COLUMNS(PCLASS,AGE,GENDER)
plt.figure(figsize=(10, 6))
sns.boxplot(x='Pclass', y='Age', hue='Gender', data=dt)
plt.title('Age Distribution by Passenger Class and Gender')
plt.show()

# USE CATPLOT METHOD AND ANALYZE THREE COLUMNS(PCLASS,SURVIVED,GENDER)
plt.figure(figsize=(10, 6))
sns.catplot(x='Pclass', hue='Survived', col='Gender', kind='count', data=dt)
plt.title('Survival Count by Passenger Class and Gender')
plt.show()

# IMPLEMENT HEATMAP AND PAIRPLOT FOR THE DATASET
plt.figure(figsize=(10, 6))
sns.heatmap(dt.corr(), annot=True, cmap='coolwarm', fmt=".2f")
plt.title('Correlation Heatmap')
plt.show()

sns.pairplot(dt)
plt.title('Pairplot of the Dataset')
plt.show()
```

## OUTPUT
![ds_exp2_1](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/40a60dd4-d3b3-4c77-8a0a-ec4f09c65af0)
![ds_exp2_2](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/12e91c1e-8653-40ff-8974-3029e26dc5f5)
![ds_exp2_3](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/4889e38d-2e13-45b3-9423-ba20eba1a19b)
![ds_exp2_4](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/a01832cb-6dee-44a4-9f0f-2aeca7e620a3)
![ds_exp2_5](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/4c7bc87e-7501-4cd9-bb75-be3f8b786613)
![ds_exp2_6](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/d037b42f-9b99-42a4-98a8-0dce8abc82c5)
![ds_exp2_7](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/11c78bd1-7ec9-4363-9a2a-8d79b5a820ad)
![ds_exp2_8](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/4e83e022-9035-40a6-8384-bab6a0fa2cde)
![ds_exp2_9](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/d2300b82-1e23-4216-a703-6aff445757e9)
![ds_exp2_10](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/5c4b8611-ce9b-4ee7-8ab1-a74004f19141)
![ds_exp_11](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/bdf44a1a-c12e-405b-bbb9-8f4edf8da394)
![ds_exp2_12](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/dc3a6b7f-55e1-4568-af53-288a29831420)
![ds_exp2_13](https://github.com/Thirukaalathessvarar-S/EXNO2DS/assets/121166390/a0d17d69-a7e7-41b6-ba9b-22abe20bced8)

# RESULT
Thus the code to execute the program is implemented successfully.
