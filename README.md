# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/f0782825-945d-4ad9-8846-23a91a96400a)
```
df = sns.load_dataset("tips")
df
```

![image](https://github.com/user-attachments/assets/f13f3cef-a978-4d5d-9c51-883b73d2cafe)

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto")
```

![image](https://github.com/user-attachments/assets/64fabce8-8725-4c81-9da8-32dec0ef605b)

```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title('Multi-line plot')
plt.xlabel(' x label')
plt.ylabel('Y label')
```
![image](https://github.com/user-attachments/assets/d33c4fcd-2af1-4c2b-ab51-d39d5c5842ba)

```
import seaborn as sns
import matplotlib.pyplot as plt
tips = sns.load_dataset('tips')
avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```

![image](https://github.com/user-attachments/assets/72c798e5-3db5-433a-b4bc-22d8615d4bcd)

```
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill',width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip',width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/e567406e-90db-419a-b4db-4470ee855403)

```
import matplotlib.pyplot as plt

years = range(2000, 2011)
apple = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.926, 0.941, 0.930, 0.923, 0.918, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896]

plt.figure(figsize=(12, 6))

# Plot stacked bar chart
plt.bar(years, apple, label='Apple', color='#ff9999')
plt.bar(years, oranges, bottom=apple, label='Oranges', color='#ffcc99')

plt.title("Stacked Bar Chart of Apple and Orange Data (2000-2011)")
plt.xlabel("Year")
plt.ylabel("Values")
plt.xticks(years)
plt.legend()
plt.show()
```

![image](https://github.com/user-attachments/assets/dd9dc59d-ae09-4f02-b0d5-69e9f1bad3c8)

```
import seaborn as sns
import matplotlib.pyplot as plt
dt = sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
plt.show()
```
![image](https://github.com/user-attachments/assets/ecc79c36-3c3e-44d2-9be4-ca62cc054d02)

```
import pandas as pd
tit=pd.read_csv("titanic.csv")
tit
```
![image](https://github.com/user-attachments/assets/c9dafe13-71c6-4f72-aed3-cbb863245346)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit,palette='rainbow')
plt.title("Fare of passenger by Embarked Town")
```

![image](https://github.com/user-attachments/assets/c5d3d43c-0eb6-4527-80ae-0753e52e20a1)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit,palette='rainbow',hue='Pclass')
plt.title("Fare of passenegers Embarked Town ,Divided by class")
```

![image](https://github.com/user-attachments/assets/383d6b6d-5005-4725-aa94-eaef2cc49ac2)

```

import seaborn as sns

tips
sns.load_dataset('tips')

sns.scatterplot(x= 'total_bill', y='tip', hue='sex',data=tips)

plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![image](https://github.com/user-attachments/assets/84f65b43-3721-4ce3-9827-ea5ea62b1618)

```
import seaborn as sns
import numpy as np
import pandas as pd
np.random.seed(1)
num_var = np.random.randn(1000)
num_var =pd.Series(num_var,name="Numerical Variable")
num_var
```

![image](https://github.com/user-attachments/assets/170f05b4-8e15-48d9-9e03-1490010d2324)

```
sns.histplot(data=num_var,kde=True)
```
![image](https://github.com/user-attachments/assets/61aa9613-78f5-4758-9016-df9f6d5e476b)

```
sns.histplot(data=df,x="Pclass",hue="Survived",kde=True)
```

![image](https://github.com/user-attachments/assets/5ad0fd84-cd5a-40db-915a-1e6c8cde3f6f)

```
import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(0)
marks = np.random.normal(loc=70,scale=10,size=100)
marks
```
![image](https://github.com/user-attachments/assets/2abf2e20-5e9a-44c5-bdf8-09eba530f3db)

![image](https://github.com/user-attachments/assets/adc6c7b7-7999-4eb7-8f0a-b7c5c02b1e6c)

![image](https://github.com/user-attachments/assets/46ac1424-2dd2-435e-b238-3ed2e73fb7a7)


![image](https://github.com/user-attachments/assets/094d4422-c450-4bbc-8d6a-2865ab1bdcc2)





# Result:
 Include your result here
