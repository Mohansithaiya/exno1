# Exno:1
## Data Cleaning Process

## NAME: MOHAN S
## REG.NO: 212223240094

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

```python
import pandas as pd
import random
import numpy as np
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![Screenshot 2025-03-04 104221](https://github.com/user-attachments/assets/756b6b12-9ad2-4f74-8f8e-ee6121536c13)

```python
df.tail()
```
![Screenshot 2025-03-04 104408](https://github.com/user-attachments/assets/5a3596ae-894f-4429-9adb-720a60c876b4)

```python
df.fillna(1)
```
![Screenshot 2025-03-04 104508](https://github.com/user-attachments/assets/6b69af02-da12-4fa7-91ce-6a37d4873e75)

```python
df.describe()
```
![Screenshot 2025-03-04 104624](https://github.com/user-attachments/assets/9a4e2d6d-b2f1-4b1c-8106-01e623044cfc)

```python
df.info()
```
![Screenshot 2025-03-04 104718](https://github.com/user-attachments/assets/3f9d625f-45e5-4562-8180-927035377347)

```python
df.count()
```
![Screenshot 2025-03-04 104806](https://github.com/user-attachments/assets/4b8281b5-11de-46f1-a3b9-162bc443c516)

```python
df.ffill()
```
![Screenshot 2025-03-04 104843](https://github.com/user-attachments/assets/ff74d164-2842-4212-96ad-158b4b265886)

```python
df.bfill()
```
![Screenshot 2025-03-04 104951](https://github.com/user-attachments/assets/f2a5e266-19a7-497e-8339-d9228cebf89f)

```python
df.isnull().sum()
```
![Screenshot 2025-03-04 105028](https://github.com/user-attachments/assets/863d0b5f-12ca-4df7-a569-abbab5a2b4d9)

```python
df.isnull().any()
```
![Screenshot 2025-03-04 105306](https://github.com/user-attachments/assets/0aa34796-3af3-43f0-a04e-46ba1859607a)

```python
df.dropna()
```
![Screenshot 2025-03-04 105341](https://github.com/user-attachments/assets/6bb9dead-809c-411c-816b-30ef8ca49635)

```python
df.fillna(method = 'ffill')
```
![Screenshot 2025-03-04 105626](https://github.com/user-attachments/assets/d355f794-f941-490f-84bc-75f3cd869ef1)

```python
df.fillna(method = 'bfill')
```
![Screenshot 2025-03-04 105713](https://github.com/user-attachments/assets/27b79a8d-6337-4bbe-96cf-f3624cfdafd6)

```python
df_dropped
```
![Screenshot 2025-03-04 105941](https://github.com/user-attachments/assets/41ad6820-46e4-4224-9012-467be15601cd)

```python
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![Screenshot 2025-03-04 110045](https://github.com/user-attachments/assets/bb40a01c-78bf-4cbc-82c6-f005204dd532)

```python
import pandas as pd
import random
import numpy as np
import seaborn as sns
df=pd.read_csv("/content/iris.csv")
df
```
![Screenshot 2025-03-04 110133](https://github.com/user-attachments/assets/5d5e6b58-a9e0-4e81-a4fb-df202dc008e4)

```python
df.describe()
```
![Screenshot 2025-03-04 110212](https://github.com/user-attachments/assets/7c8406d9-3da7-44e4-8e21-298334a34531)

```python
df.isnull()
```
![Screenshot 2025-03-04 110253](https://github.com/user-attachments/assets/a78c270f-7d99-479c-94a7-aab36f7cee09)

```python
sns.boxplot(x='sepal_width',data=df)
```
![Screenshot 2025-03-04 110327](https://github.com/user-attachments/assets/d7a8d7f2-8a95-4bbc-9564-3812bbc2f923)


```python
c1=df.sepal_width.quantile(0.25)
c3=df.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![Screenshot 2025-03-04 110407](https://github.com/user-attachments/assets/b9cf0fc5-1979-4373-ac49-c3a58bc90a1f)

```python
rid=df[((df.sepal_width<(c1-1.5*iq))|(df.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![Screenshot 2025-03-04 110450](https://github.com/user-attachments/assets/26bf21fc-7b07-4068-9ea8-4848f07edbbd)

```python
delid=df[~((df.sepal_width<(c1-1.5*iq))|(df.sepal_width>(c3+1.5*iq)))]
delid
```
![Screenshot 2025-03-04 110521](https://github.com/user-attachments/assets/051f7200-8434-4df1-882c-eed528516b01)

```python
sns.boxplot(x='sepal_width',data=delid)
```
![Screenshot 2025-03-04 110554](https://github.com/user-attachments/assets/19cad68f-ec46-44b5-b0fa-c9a95f58bddd)


```python
import matplotlib.pyplot as plt
import pandas as pd
import random
import numpy as np
import scipy.stats as stats
df=pd.read_csv("/content/heights (1).csv")
df
```
![Screenshot 2025-03-04 110637](https://github.com/user-attachments/assets/5a0fe5c1-3b20-49c3-8205-8619b19507a5)

```python
z=np.abs(stats.zscore(df['height']))
z
```
![Screenshot 2025-03-04 110801](https://github.com/user-attachments/assets/a12376a7-3e53-462f-b029-742c277afd91)

```python
df1=df[z<3]
df1
```
![Screenshot 2025-03-04 110857](https://github.com/user-attachments/assets/e2be254c-5d9f-49b0-a57b-9296ae26fbca)


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
