# Heart-Attack-Analysis-Prediction

<a id=0.1></a>
1. [Introduction](#1) 
    - 1.1 [About Data](#2)
    - 1.2 [About the Problem](#3)
2. [Data Preparation](#4)
3. [Exploratory Data Analysis](#5)
4. [Data Preprocessing](#6)
5. [Modeling](#7)
    - 5.1 [Linear Classifiers](#8)
    - 5.2 [Tree Models](#9)
    

## 1. Introduction <a id=1></a>
[back to top](#0.1)

### 1.1 About Data <a id=2></a>

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

### 1.2 About the Problem <a id=3></a>
To perform EDA and predict if a person is prone to a heart attack or not.

## 2. Data Preparation <a id=4></a>
[back to top](#0.1)

- Checking for any null values
- Checking any missing data
- Checking the number of unique values in each column
- Separating the columns in categorical and continuous

### 3. Exploratory Data Analysis <a id=5></a>
[back to top](#0.1)
