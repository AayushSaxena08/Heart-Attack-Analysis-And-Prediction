# Heart-Attack-Analysis-Prediction

<a id=0.1></a>
1. [Introduction](#1) 
    - 1.1 [About Data](#1.1)
    - 1.2 [About the Problem](#1.2)
2. [Data Preparation](#2)
3. [Exploratory Data Analysis](#3)
    - 3.1 [Conclusions from the EDA](#3.1)
4. [Data Preprocessing](#4)
5. [Modeling](#5)
    - 5.1 [Linear Classifiers](#5.1)
    - 5.2 [Tree Models](#5.2)
    

## 1. Introduction <a id=1></a>
[back to top](#0.1)

### 1.1 About Data <a id=1.1></a>

You can download the dataset -------> [Link](https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset)

`age` - Age of the patient

`sex` - Sex of the patient

`cp` - Chest pain type ~ 0 = Typical Angina, 1 = Atypical Angina, 2 = Non-anginal Pain, 3 = Asymptomatic

`trtbps` - Resting blood pressure (in mm Hg)

`chol` - Cholestoral in mg/dl fetched via BMI sensor

`fbs` - (fasting blood sugar > 120 mg/dl) ~ 1 = True, 0 = False

`restecg` - Resting electrocardiographic results ~ 0 = Normal, 1 = ST-T wave normality, 2 = Left ventricular hypertrophy

`thalachh`  - Maximum heart rate achieved

`oldpeak` - Previous peak

`slp` - Slope

`caa` - Number of major vessels 

`thall` - Thalium Stress Test result ~ (0,3)

`exng` - Exercise induced angina ~ 1 = Yes, 0 = No

`output` - Target variable

### 1.2 About the Problem <a id=1.2></a>
To perform EDA and predict if a person is prone to a heart attack or not using linear and tree based models

## 2. Data Preparation <a id=2></a>
[back to top](#0.1)

- Checking for any null values
- Checking any missing data
- Checking the number of unique values in each column
- Separating the columns in categorical and continuous

## 3. Exploratory Data Analysis <a id=3></a>
[back to top](#0.1)

### 3.1 Conclusions from the EDA <a id=3.1></a>

1. There are no NaN values in the data.
2. There are certain outliers in all the continuous features.
3. The data consists of more than twice the number of people with `sex` = 1 than `sex` = 0.
4. There is no apparent linear correlation between continuous variable according to the heatmap.
5. The scatterplot heatmap matrix suggests that there might be some correlation between `output` and `cp`, `thalachh` and `slp`.
6. It is intuitive that elder people might have higher chances of heart attack but according to the distribution plot of `age` wrt `output`, it is evident that this isn't the case.
7. According to the distribution plot of `thalachh` wrt `output`, people with higher maximum heart rate achieved have higher chances of heart attack.
8. According to the distribution plot of `oldpeak` wrt `output`, people with lower pevious peak achieved have higher chances of heart attack.
9. The plot *3.2.4* tells about the following -
    - People with Non-Anginal chest pain, that is with `cp` = 2 have higher chances of heart attack.
    - People with 0 major vessels, that is with `caa` = 0 have high chance of heart attack.
    - People with `sex` = 1 have higher chance of heart attack.
    - People with `thall` = 2 have much higher chance of heart attack.
    - People with no exercise induced angina, that is with `exng` = 0 have higher chance of heart attack.

## 4. Data Preprocessing <a id=4></a>
[back to top](#0.1)

- Feature Scaling is required

        ### define the columns to be encoded and scaled
        cat_cols = ['sex','exng','caa','cp','fbs','restecg','slp','thall']
        con_cols = ["age","trtbps","chol","thalachh","oldpeak"]

        ### encoding the categorical columns
        df1 = pd.get_dummies(df1, columns = cat_cols, drop_first = True)

        ### defining the features and target
        X = df1.drop(['output'],axis=1)
        y = df1[['output']]

        ### instantiating the scaler
        scaler = sklearn.preprocessing.RobustScaler()

        ### scaling the continuous featuree
        X[con_cols] = scaler.fit_transform(X[con_cols])

## 5. Modelling <a id=5></a>
[back to top](#0.1)

We will use Linear Classifiers - Support Vector Classifier, Logistic Regression as well as Tree Based Models - Decision Tree Classifier

### 5.1 Linear Models <a id=5.1></a>

- Support Vector Classifier - Also implemented GridSearchCV for hyperparameter tuning ( Accuracy: 0.838435 )
- Logistic Regression - Implemented LR to check the probabilities. Also used ROC curve to check for TPR and FPR ( Accuracy: 0.901639 )

### 5.2 Tree Models <a id=5.2></a>

- Decision Tree Classifier - ( Accuracy: 0.786885 )
- Random Forest Classifier - ( Accuracy: 0.786885 )
- Gradient Boosting Classifier - without tuning - ( Accuracy: 0.868852 )


## Please check the .ipynb file for code 
