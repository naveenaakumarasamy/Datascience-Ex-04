# ODD2023-Datascience-Ex-04
# Ex-04-Multivariate-Analysis
## AIM
To perform Multivariate EDA on the given data set.

## Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8
Save the final data set into the file

# PROGRAM
Developed by : Naveenaa A K
reg .no : 212222230094
```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
from google.colab import files
uploaded = files.upload()
```
![1](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/7ce83188-1f05-4c83-b0c0-8cab621a6503)
```
df = pd.read_csv('diabetes.csv')
df
```
![2](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/7203478a-f1a0-4c5c-88fa-b40bf6dbbadd)
```
df.isnull().sum()
```
![3](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/7fe2e1c3-7649-451a-8723-8775091f593e)
```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![4](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/2ab18535-def0-4de9-9683-ac542bbbc499)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
```
![5](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/0d076a54-8d1d-429f-b779-9d9d2fd936d8)
```
sns.boxplot(df)
```
![6](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/c0b41fc0-9962-41b7-9c72-7c1f06425f07)
```
plt.figure(figsize = (14,6))
sns.scatterplot(x = 'Glucose',y='BloodPressure',data = df)
```
![7](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/8a782e4b-464f-41c5-aac5-32726540808a)
```
sns.scatterplot(x = 'Glucose',y='Insulin',data = df)
```
![8](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/d08be74e-bb3d-411b-adf6-1effdd4facca)
```
sns.scatterplot(x = 'Glucose',y='DiabetesPedigreeFunction',data = df)
```
![9](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/2c22ff67-7005-4d68-bbc9-840c9953e5c0)
```
sns.scatterplot(x = 'Glucose',y='Age',data = df)
```
![10](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/ee966e75-1339-46ce-a704-7c10acf279a0)
```
sns.heatmap(df.corr(),annot = True)
```
![11](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/b1f1498b-1170-4f94-8f43-ba9aa3056bcf)
```
from google.colab import files
uploaded = files.upload()
```
![12](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/5049c3f3-e11e-4a58-aefa-7790d6ffe9cc)
```
df = pd.read_csv('employeesal.csv')
df
```
![13](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/963ec82b-4046-473c-a319-a0d0d4474a37)
```
df.isnull().sum()
```

![14](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/6299e8e0-352c-49fb-bf62-7479e816905e)
```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```

![15](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/cb0b0f54-60ec-4f36-a1cb-75a1cecef155)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```

![16](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/f452c419-bbdf-4b63-8c43-85f8bee9dc16)
