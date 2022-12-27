# Heart-Attack-Analysis-Prediction

<a id=0.1></a>
1. [Introduction](#1) 
    - 1.1 [About Data](#2)
    - 1.2 [About the Problem](#3)
2. [Data Preparation](#4)
3. [Exploratory Data Analysis](#5)
    - 3.1 [Conclusions from the EDA](#6)
5. [Data Preprocessing](#7)
6. [Modeling](#8)
    - 5.1 [Linear Classifiers](#8.1)
    - 5.2 [Tree Models](#8.2)
    

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

## 3. Exploratory Data Analysis <a id=5></a>
[back to top](#0.1)

### 3.1 Conclusions from the EDA <a id=6></a>
[back to top](#0.1)

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


#### 5.2 Tree Models <a id=17></a>
