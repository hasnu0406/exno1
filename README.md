# Exno:1
Data Cleaning Process
### NAME: HASNA MUBARAK AZEEM
### REG NO.: 212223240052
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

# Coding and Output:
```
import pandas as pd
df=pd.read_csv("Data_set.csv")
df
```
![image](https://github.com/user-attachments/assets/fc079894-7cfe-4e7b-b0f5-4d737eee2bea)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/cb1ffa5d-0247-49cf-a523-2fcb0cfa5202)

```
df.info()
```
![image](https://github.com/user-attachments/assets/e5056484-f8b6-4eb5-824a-c18a4846e9ac)

```
df.head()
```
![image](https://github.com/user-attachments/assets/7e8840a8-bb65-4b51-b68f-ea85e956d572)

```
df.tail()
```
![image](https://github.com/user-attachments/assets/dcc5b02c-d810-4973-9991-ca82566ef248)

```
df.isnull()
```
![image](https://github.com/user-attachments/assets/3c56c4e1-9dc1-4e6f-aacb-2a7c9d3da790)

```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/2074150b-989d-4d8b-b3b0-e2855988baba)

```
df.notnull()
```
![image](https://github.com/user-attachments/assets/6d45c24f-8b00-4430-8634-f3d52fc671ee)

```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/61430121-fd18-47c2-95ae-3e4ff23d6afd)

```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/cf13c792-46f3-4729-a0f6-9bb045a10208)

```
df.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/725de920-5472-4f86-b929-3954ceb2bf1a)

```
df.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/6e0fd86d-b72c-4ff7-834b-241d44b11561)

```
df['watchers'].fillna(value=df['watchers'].mean())
```
![image](https://github.com/user-attachments/assets/ec1b37e1-2c81-4b46-81f7-5da86275bf9f)

```
df['watchers'].fillna(value=df['watchers'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/c03b594b-d1f1-4517-acba-4771da4d865a)

```
df['num_episodes'].fillna(value=df['num_episodes'].mean())
```
![image](https://github.com/user-attachments/assets/2b132216-f0e4-49ec-b635-cdcad57f002f)

```
df['num_episodes'].fillna(value=df['num_episodes'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/cdd268d1-3670-4548-bca2-5481053423a5)

```
df['rating'].fillna(value=df['rating'].mean())
```
![image](https://github.com/user-attachments/assets/6bdd9048-67ce-4fd2-b553-7825c4f041de)

```
df['rating'].fillna(value=df['rating'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/478ab7a4-eb85-45f0-bdee-10dbde192b77)

```
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean())
```
![image](https://github.com/user-attachments/assets/88dfdd3d-f9e4-42cf-84fc-03d7c0ddfc71)

```
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/4a5d4453-b855-406f-90ba-593da3277a5f)

```
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
```
![image](https://github.com/user-attachments/assets/dd37b5ce-536a-42be-b65d-c05b3d4f4b11)

```
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/6943038d-4be1-4ef2-b102-974fd8cae8db)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/user-attachments/assets/a0e741e3-7c4c-458f-971f-36a31499275c)

```
sns.boxplot(data=af)
```
![image](https://github.com/user-attachments/assets/cdf946c8-b745-428d-ba5d-830cd02dc84c)

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/eedcfa96-f8f8-4eec-b80c-a85ecdd9ebd4)

```
lb=q1-1.5*iqr
ub=q3+1.5*iqr
lb
```
![image](https://github.com/user-attachments/assets/9a96b7f9-8a92-4a64-87b2-1611c7d3c4a7)

```
ub
```
![image](https://github.com/user-attachments/assets/0e04b003-2b90-4821-a913-13dda4923fbc)

```
af=af[((af>=lb)&(af<=ub))]
af
```
![image](https://github.com/user-attachments/assets/87230f50-23d9-4b7a-b015-b56ef3082d5b)

```
af.dropna()
```
![image](https://github.com/user-attachments/assets/f97ebf86-8d66-46d6-b9c8-3acd5dbd3ae4)

```
sns.boxplot(data=af)
```
![image](https://github.com/user-attachments/assets/75b987b5-1e20-4d58-b34b-6645fbcaebbd)

```
from scipy import stats
import numpy as np
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df 
```
![image](https://github.com/user-attachments/assets/dad5b996-2d79-4af8-b8ec-dc1de6232e96)

```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```
![image](https://github.com/user-attachments/assets/5efd4856-e454-4c4d-be26-434e248409f3)

```
val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,258]

out=[]
def d_o(val):
    ts=3
    m=np.mean(val)
    sd=np.std(val)
    for i in val:
        z=(i-m)/sd
        if np.abs(z)>ts:
            out.append(i)
    return out

op=d_o(val)
op
```
![image](https://github.com/user-attachments/assets/fb808ff7-6f9f-49a4-85b9-1f3e17b41d95)

















# Result
Thus, the Data Cleaning Process is executed Successfully.
