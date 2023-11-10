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







