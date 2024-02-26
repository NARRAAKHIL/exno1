# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![output 1](https://github.com/chgeethika/ex-no1/assets/142209368/cc27d6cf-05b5-4b55-9c0a-2c03001688f9)
```
print(df.head(7))
```
![o 3](https://github.com/chgeethika/ex-no1/assets/142209368/ad269980-fb09-4705-991a-7076f0b28700)
```
print(df.tail(2))
```
![o4](https://github.com/chgeethika/ex-no1/assets/142209368/99c1ad9e-d98c-44a3-96a5-61a8622d6178)
```
df.info()
```
![o5](https://github.com/chgeethika/ex-no1/assets/142209368/811fbadb-3961-4c7d-b945-60ef2d52005c)
```
print(df.describe())
```
![o6](https://github.com/chgeethika/ex-no1/assets/142209368/0c207343-ef54-4b43-b547-1a5af544a062)
```
df.isnull().sum()
```
![o7](https://github.com/chgeethika/ex-no1/assets/142209368/87c68baa-7624-4e1a-971a-80c83eb61d90)
```
df.nunique()
```
![o8](https://github.com/chgeethika/ex-no1/assets/142209368/9d9493c9-6e0b-4ee6-89be-17cbd2e5e56d)
```
mn=df.TOTAL.mean()
mn
```
![mn](https://github.com/chgeethika/ex-no1/assets/142209368/37a126cd-8ea9-4c65-af75-2697bddd6a35)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![o9](https://github.com/chgeethika/ex-no1/assets/142209368/52bc6f65-7e58-4246-b74d-aaab99b4fb0d)
```
min=df.M4.min()
min
```
![min](https://github.com/chgeethika/ex-no1/assets/142209368/3571db1b-b18c-439e-814b-4ecc847615c4)
```
df.M4.fillna(min,inplace=True)
df
```
![o10](https://github.com/chgeethika/ex-no1/assets/142209368/193b4f4d-cb59-4493-bafe-2c3aebb9c503)

![o10](https://github.com/chgeethika/ex-no1/assets/142209368/5a0746c8-ed4d-4dc3-a67f-c6e9656ce551)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![o12](https://github.com/chgeethika/ex-no1/assets/142209368/35531f01-5402-4cc1-991f-a07e62dacf48)
```
sns.boxplot(data=af)
```
![o13](https://github.com/chgeethika/ex-no1/assets/142209368/32e94065-fd93-4f9e-93ec-5f3894e955b4)

```
sns.scatterplot(data=af)
```
![o14](https://github.com/chgeethika/ex-no1/assets/142209368/3d0adb77-0703-44c3-9261-f74cb1f0b920)
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![o15](https://github.com/chgeethika/ex-no1/assets/142209368/225a452e-83d4-4210-8748-e8add5b925e1)
```
af=af[((af>=low)&(af<=high))]
af
```
![o16](https://github.com/chgeethika/ex-no1/assets/142209368/49056f63-9937-4109-a285-8c4388441f46)
```
af.dropna()
```
![o17](https://github.com/chgeethika/ex-no1/assets/142209368/466a854d-4b2f-43c8-85f8-ac94ad6e38d5)
```
sns.boxplot(data=af)
```
![o18](https://github.com/chgeethika/ex-no1/assets/142209368/7b62062c-59cc-4789-bbcf-5e4fd63c0b53)

```
sns.scatterplot(data=af)
```
![o19](https://github.com/chgeethika/ex-no1/assets/142209368/d294460b-cd0a-4f8e-8ea7-495169adb75c)
```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![o20](https://github.com/chgeethika/ex-no1/assets/142209368/bff14676-97ae-4ebd-9897-89d9e8a3bc87)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![o22](https://github.com/chgeethika/ex-no1/assets/142209368/9a5242a4-f1c6-4ffa-96b1-fa68c0aa81ab)

# Result
Thus the given program executed successfully.
