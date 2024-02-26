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
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/7c373076-e65c-40e3-8df6-dc2b27b73166)

```
print(df.head(7))
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/7074af7a-5a2a-4bff-ac4c-6a5767edac2f)

```
print(df.tail(2))
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/2e9e55b9-6c96-4eb0-92b6-41525b6c90a4)

```
df.info()
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/58d0f021-bc43-4bcd-92a0-55b6b5cb9685)

```
print(df.describe())
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/1ba78e10-3963-439c-918c-b2ac1d4ac528)

```
df.isnull().sum()
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/d599e72b-c5ef-4007-b54e-667eeb7d40fe)

```
df.nunique()
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/eaa77e9c-6025-49cd-9421-1f3158356f8a)

```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/ca7fc9c7-c6d5-4eb9-8533-8e163c83bef8)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/8dd52325-943b-48a6-9b2b-509d98a19e9b)

```
min=df.M4.min()
min
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/e1118c54-e94c-4497-ae3c-d74b80ca5a6b)

```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/5fb8a533-1e90-4670-918d-43360cc9187f)


![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/551a4482-620e-4073-befd-cdfddff2ced0)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```

![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/e1e0de8e-8d46-4395-94db-14ed6a8fec94)

```
sns.boxplot(data=af)
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/47e6a554-6c98-4910-a293-3df7b559170e)


```
sns.scatterplot(data=af)
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/6c106b7c-f20f-457b-8e82-030953b196f4)

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
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/9bcb5980-504c-495c-9c94-fc5a9715b867)

```
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/c3ede186-1c35-4acb-b8a0-63480a7c06dd)

```
af.dropna()
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/37ee91c2-07f5-4eae-af34-895e1a695268)

```
sns.boxplot(data=af)
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/c8236ba2-bac3-4f79-87a2-50f889632fd0)

```
sns.scatterplot(data=af)
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/efa0c942-8da0-4402-b8b9-ed898855860f)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/4fd4bc5f-f175-4de3-afa8-2a61a20f7535)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/NARRAAKHIL/exno1/assets/144979843/c498027d-785e-4a0a-b136-a1da79bee45e)

# Result
Thus the given program executed successfully.
