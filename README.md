# Mini-Project
# ANALYSIS OF POSITION OF A EMPLOYEE IN A COMPANY
# Aim:
 Analysis Of Position Of  a employee in a company.
 
# ALGORITHM:
Step:1  Importing necessary packages.

Step:2  Read the data set.

Step:3  Execute the methods.

Step:4  Run the program.

Step:5  Get the output.

# CODE AND OUTPUT:
```python
import pandas as pd
df = pd.read_csv("Salary.csv")

df.head(5)
```
<img width="159" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/561a25f6-fdce-4054-b772-c686f6a896ba">

```python
df.info()
```
<img width="173" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/d624c06b-0c51-492c-98ed-3dc32ef6a4a0">

```python
df.dropna(how='all').shape
```
<img width="42" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/671085fe-4669-4f87-95b2-aa19c0d9e6da">

```python
df.fillna(0)
```
<img width="161" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/3225c71c-92bc-4880-b44b-56cc5c24b36e">

```python
df.fillna(method='bfill')
```
<img width="163" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/170c83b6-cc4d-42ce-a836-e302381bbf2f">

```python
df.duplicated()
```
<img width="67" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/689217ce-0a64-4fef-a72f-99dd09ec9a8d">

```python
mn=df.Salary.mean()
mn
```
<img width="50" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/63d57ed4-1cde-4e78-a355-373a99f0e099">

```python
exp = [13,23,28,12,5,9,31,26,10,19,22,24,29,4,25,30]
af=pd.DataFrame(exp)
af
```
<img width="50" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/6fb66744-d910-4502-aa43-78c0219abd46">

```pyhton
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1

low=q1-1.5*iqr
low
```
<img width="71" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/2ad03cb8-b54d-420c-ad5b-2dff43a1fbd7">

```python
high=q1+1.5*iqr
high
```
<img width="77" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/a22a2710-ffe9-4c87-9ea1-d8978d3d7536">

```python
sns.boxplot(data=af)
```
<img width="211" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/551846cc-c8c1-44d5-b3fb-ff92d1c912fd">

```python
import pandas as pd
import matplotlib.pyplot as plt


data = pd.read_csv("Salary.csv")


plt.figure(figsize=(8, 4))
data['Position'].value_counts().plot(kind='bar')
plt.title('Distribution of Positions')
plt.xlabel('Position')
plt.ylabel('Count')
plt.show()
```
<img width="260" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/602ff4ae-c669-4eb8-b292-0af0952c8906">

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

sns.pairplot(data, hue="Position")
plt.show()
```
<img width="254" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/4527c40e-031c-4e4f-9340-326184bdce45">

```python
correlation_matrix = data.corr()
plt.figure(figsize=(8, 6))
sns.heatmap(correlation_matrix, annot=True, cmap="coolwarm")
plt.title("Correlation Matrix")
plt.show()
```
<img width="739" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/0de38c2a-bd26-489d-b526-0846072540bc">

```python
import pandas as pd
from sklearn.preprocessing import StandardScaler

numerical_features = ['Level', 'Salary']
scaler = StandardScaler()
data[numerical_features] = scaler.fit_transform(data[numerical_features])
data
```
<img width="121" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/21468aab-ad5a-4654-90d7-e214c0fbddc5">

```python
from sklearn.preprocessing import MaxAbsScaler

scaler = MaxAbsScaler()
columns_to_scale = ['Level', 'Salary']
data[columns_to_scale] = scaler.fit_transform(data[columns_to_scale])
data
```
<img width="119" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/4ae0b522-1fcc-4c1b-8237-20f004fe4505">

```python
from sklearn.preprocessing import RobustScaler

scaler = RobustScaler()
data[['Level', 'Salary']] = scaler.fit_transform(data[['Level', 'Salary']])
data
```
<img width="118" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/2f059514-26ed-4d2e-8d2f-8c0c1653d930">

```python
data.skew()
```
<img width="902" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/72db6239-3360-4ff2-a18e-54c9a8a0bacc">

```python
import matplotlib.pyplot as plt
import seaborn as sns
import statsmodels.api as sm
import scipy.stats as stats
import numpy as np

np.log(df["Salary"])
```
<img width="94" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/dedc1bda-fd57-4cef-8a7b-9294bf4bf26d">

```python
np.sqrt(df["Salary"])
```
<img width="91" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/fc913b87-446c-4c57-99df-0bf32df06771">

```python
sm.qqplot(df['Salary'],line='45')
plt.show()
```
<img width="215" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/4da76c2a-f914-4b1c-8a46-2ed8f7a101ff">

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(8, 4))
plt.hist(data['Salary'], bins=10, color='skyblue', edgecolor='black')
plt.title('Salary Distribution')
plt.xlabel('Salary')
plt.ylabel('Frequency')
plt.show()
```
<img width="256" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/6c50c172-b5d4-420b-a684-5f7f501c9c89">

```python
plt.figure(figsize=(8, 4))
sns.boxplot(data=data, x='Salary', color='lightcoral')
plt.title('Salary Boxplot')
plt.xlabel('Salary')
plt.show()
```
<img width="241" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/5163c29f-34c5-4aa7-aa9e-ad6d3dc35170">

```python
plt.figure(figsize=(10, 4))
sns.countplot(data=data, x='Position', palette='Set2')
plt.title('Position Counts')
plt.xlabel('Position')
plt.ylabel('Count')
plt.show()
```
<img width="317" alt="image" src="https://github.com/TejaswiniGugananthan/Mini-Project/assets/121222763/1d21f7dc-5eaa-4e6d-b25e-3816a412db79">





# Result:
Hence the program to analyze the data set using data science is applied sucessfully.


