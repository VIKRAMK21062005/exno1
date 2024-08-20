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
![image](https://github.com/user-attachments/assets/b903e531-22de-46ef-9e30-f6da7da86e4c)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/3c602648-5226-46af-bea5-722ddf2fe806)
```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/df19bcd6-551a-48f0-b380-00c162aeeb6d)
```
df.dropna()
```
![image](https://github.com/user-attachments/assets/df19bcd6-551a-48f0-b380-00c162aeeb6d)
```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/add8dc6d-01a8-4dac-b115-4f63d6056074)
```
df.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/ded14828-eeb4-4b08-aac4-d1cbf35f3b09)
```
df.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/f784c0f4-56ff-4435-8c81-990271a8bb34)
```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/99546284-f891-44e0-9f78-376aaa3853d8)
```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![image](https://github.com/user-attachments/assets/eec90623-3203-49e8-8420-dadc43b13d5c)
## Secound Dataset
```
import pandas as pd
import seaborn as sns
ir=pd.read_csv('iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/de8a5b58-d1ec-431d-abd5-34d62a6a1d52)
```
ir.describe()
```
![image](https://github.com/user-attachments/assets/8a7f6368-29bc-4590-b3ae-4c47631142aa)
```
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/df729162-5f75-49e2-ad91-49096a8f314c)
```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![image](https://github.com/user-attachments/assets/62fa4e5f-59b3-46eb-89ff-1a88db26c953)
```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![image](https://github.com/user-attachments/assets/4a634db2-b25b-4df7-9796-d9fd53565804)
```
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/7e417ff3-1078-47c0-99f7-042444c1aa44)


# Result
           Thus we have cleaned the data and removed the outliers by detection using IQR method.
