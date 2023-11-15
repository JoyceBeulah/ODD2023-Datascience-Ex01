# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT

```
NAME : R . JOYCE BEULAH
REG NO : 212222230058
```
```
import pandas as pd
df = pd.read_csv("SAMPLEDS - Sheet1.csv")
df.shape
```
<img width="74" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/a008f8d4-8982-4828-8a2d-ec333f890316">

```
df.head()
```
<img width="241" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/92b5047f-e3cb-465e-a261-420c7b6c8543">

```
df.tail()
```
<img width="235" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/3ba51905-6aef-4380-8c0d-17b405ad8780">

```
df.dropna(how='any').shape
```
<img width="64" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/09ceaa8a-c4a1-4571-a776-4059ea391a98">

```
x=df.dropna(how='any')
x
```
<img width="240" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/3d77557e-9e67-40e5-9d73-d50db9dcecc5">

```
df.dropna(how='all').shape
```
<img width="47" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/4be385c2-71c6-466b-95a5-47cdfa190e14">

```
tot=df.dropna(subset=['TOTAL'],how='any')
tot
```
<img width="234" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/7ef47a18-f757-4f1f-b5f6-e47270af3748">

```
tot=df.dropna(subset=['M1','M2','M3','M4'],how='any')
tot
```
<img width="232" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/b8cd8ef7-d59d-4770-9d50-8d05c2e91385">

```
df.fillna(0)
```
<img width="238" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/0caa1100-5d89-4af3-9383-4b4a5e0bfbd1">

```
df.fillna(method='ffill')
```
<img width="234" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/f502dd8b-dd3f-46d7-8548-dee8d7dc6f28">

```
df.fillna(method='bfill')
```
<img width="233" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/c6af1570-9ebc-4d1d-8cdb-e0118a11598a">

```
mn=df.TOTAL.mean()
mn
```
<img width="43" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/c46f8bee-3c60-44ba-91d2-a74d43bb0af3">

```
df.TOTAL.fillna(mn,inplace=True)
df
```
<img width="241" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/707bd271-48bd-41a6-b048-107100020d44">

```
df.duplicated()
```
<img width="50" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/120e896a-6112-41fb-bc6d-382d26cdeb72">

```
df.drop_duplicates(inplace=True)
df
```
<img width="237" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/d3436d80-4b8d-4736-9954-248f3c4d0fe1">

```
df['cd']=pd.to_datetime(df['DOB'])
df
```
<img width="238" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/95912b34-d536-420f-8583-077f5641ae90">

```
for x in df.index:
  if df.loc[x,"AVG"]>100:
    df.drop(x,inplace=True)
df
```
<img width="234" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/39ad16fa-7b47-4149-8184-c38625350e49">

```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
<img width="190" alt="image" src="https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/25ec35d3-116d-43bd-8b1e-45d0f495a845">


## RESULT
Thus,the given data is read,cleansed and the cleaned data is saved into the file.
