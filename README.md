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
# Diabetes.csv file :

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
```
sns.boxplot(numeric_cols)
```
![17](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/bed6c4f9-9448-46f8-bd57-4dc00729f7af)
```
sns.scatterplot(x = 'Salary',y='Age',data = numeric_cols)
```
![18](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/5c1d2759-1ff1-458e-bea1-8aae2c88dec9)
```
sns.scatterplot(x = 'Experience_Years',y='Salary',data = numeric_cols)
```
![19](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/03e12a08-834e-46e9-b00f-b8e85ab33a44)
```
sns.scatterplot(x = 'Experience_Years',y='Age',data = numeric_cols)
```
![20](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/360a9258-2b26-4286-b8fe-e1dfff976c87)
```
sns.heatmap(numeric_cols.corr(),annot = True)
```
![21](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/276e96e1-f8bd-4358-a7ab-8deba81f8454)
```
from google.colab import files
uploaded = files.upload()
```
![22](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/070e1037-7270-4d1a-8dfd-44767290745f)
```
df = pd.read_csv('SuperStore.csv')
df
```
![23](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/e950c416-9261-4ba3-ab17-4a161c86b168)
```
df.isnull().sum()
```
![24](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/547659e9-026b-401b-b88f-056caece545a)
```
df.dropna()
```
![25](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/840e4d74-913f-4a1d-b071-301aa0e07772)
```
df.dtypes
```
![26](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/074747bd-9a1c-46ed-bb65-b4230dd064a3)
```
numeric_cols = df.select_dtypes(include=[int,float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![27](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/edfc7b2b-85fa-4ef1-b5d1-4e9221593aec)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
sns.boxplot(numeric_cols)
```
![28](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/cde829c2-81dc-4509-b8a1-a5893362d2e9)
```
sns.heatmap(numeric_cols.corr(),annot = True)
```
![29](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/3f6e6f9f-125b-424c-9d5e-8605085697ef)

# SuperStore.csv file:
Developed by: Naveenaa A.K
Reg. No: 212222230094
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore.csv")
df=pd.DataFrame(data)
df.head()
```
![Screenshot 2023-10-07 090054](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/7306ec31-bfaf-41ab-85dc-51b8a0507170)
```
df.info()
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/715360fc-f4c8-4b4b-b159-8cd8e7321006)
```
df.describe()
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/bc14c31a-1be0-4036-a461-5114b1b78f1a)
```
df.isnull().sum()
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/35cfc39a-f452-4c9c-ac62-7dfb15734a07)
```
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/d250cfde-daa8-450b-9b6e-f51e22899562)
```
sns.scatterplot(x=df['Region'],y=df['Sales'])
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/5b398d52-5efa-4ce8-9a9f-44590d0ce957)
```

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/c7759f04-4815-48e4-9961-4b9c56044087)
```
states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/59334cd8-d12c-4302-a238-a252afb1bc61)
```
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/00dd2827-3f36-4d66-b8fb-5f54df2b435b)
```
sns.boxplot(x=df['Ship Date'],y=df['Sales'])
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/bfd2d375-b81d-42e4-ad71-c05f55401011)
```
sns.displot(df, x="Region", hue="Category")
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/6c3a12f4-d031-4d04-b5fa-b5a0639d9eed)
```
df.corr()
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/dafb235f-0706-4254-bfd1-473c48e40aff)
```
sns.heatmap(df.corr(),annot=True)
```
![image](https://github.com/naveenaakumarasamy/Datascience-Ex-04/assets/113497406/df8298c8-d4fd-45b2-b6fb-811c0e50a73d)

## RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
