# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE AND  OUPUT:

```
Name: ARAVIND SAMY .P
Reg no:212222230011
```
```
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
print(df)
```
<img width="230" alt="278807457-1b3fbb99-9a74-4b53-8ce2-497d3d66105e" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/e5951e63-ebb8-4a56-838b-3aa434b5eaa2">

```
df.isnull().sum()
```
<img width="74" alt="278807508-6bde75cc-013e-40a1-a33f-c2d87d475f84" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/0c60fd95-c1cc-4916-9112-938f53e29b29">


```
\plt.figure(figsize=(5,5))
plt.title("data with outliners")
df.boxplot()
plt.show()
```
<img width="218" alt="278807545-eee15327-56f0-41cd-8ac6-b521415b95fb" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/04311652-8670-40fe-9a9b-a2b129ca9de0">
```
plt.figure(figsize=(5,5))
cols=["size","tip","total_bill"]
q1=df[cols].quantile(0.25)
q3=df[cols].quantile(0.75)
iqr=q3-q1
df=df[~((df[cols]<(q1-1.5*iqr))|(df[cols]>(q3+1.5*iqr))).any(axis=1)]
plt.title("dataset after removing outliners")
df.boxplot()
plt.show()
```
<img width="218" alt="278807616-7927a9a1-2722-43d4-8917-ea4d9e6f0450" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/77efd8be-3ee1-48a1-99d6-d972e53b7786">

```
sns.barplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="center")
plt.title("highest total bill amount by day of the week")
```



<img width="283" alt="278807645-ea4ba09f-7399-4a56-8f27-a2185acb7016" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/fd75313e-4236-4887-a5ae-20d2397aa7e0">

```
sns.boxplot(x=df["smoker"],y=df["tip"],hue=df["smoker"])
plt.title("average tip amount given by smokers and non-smokers")
```


<img width="280" alt="278807697-3ef7ca9a-79d7-43e8-b4ff-0efcbf23dfcc" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/43426553-34bf-41d8-9ec3-98e8b3f1b0db">

```

df["tip_percent"]=df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'], y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```
<img width="289" alt="278807741-85297eb7-efe1-4495-a2d6-4576d383d014" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/9e8f05d7-9857-4ed7-bc66-ffa157175340">


```


sns.boxplot(x=df["sex"],y=df["tip"],hue=df["sex"])
plt.title("tips based on gender")
```
<img width="279" alt="278807799-04734581-41dd-4f5b-b2e4-85afc1bb9093" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/147c9180-584e-42ad-a1cb-03bfbf87abc1">

```

sns.scatterplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="best")
plt.title("total bill amount by day of te week")

```



<img width="293" alt="278807838-2fda0016-1b0c-45e9-9f26-102c96d4c22c" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/0639d7dc-f97c-4454-85fe-dc192de24bdd">

```

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()
```
<img width="293" alt="278807865-7d378417-a9a6-4a10-909a-83d61a1e9da9" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/44b69284-e01f-4174-8ada-31db2263d31d">

```
sns.barplot(x=df["size"],y=df["total_bill"],hue=df["size"])
plt.title("average total bill amount by dinning party size")

```
<img width="286" alt="278807884-0c0dbc52-ce62-4957-9da0-dc77048fd09e" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/52123ac3-2a1e-46a3-9231-8170ba24ae86">

```
sns.barplot(x=df["size"],y=df["total_bill"],hue=df["size"])
plt.title("average total bill amount by dinning party size")


```

<img width="278" alt="278807916-f24cff71-ea97-44d8-8c43-5fe29d3fb0ba" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/a4437892-72f3-4ee5-844c-943a1093dcb2">

```

sns.violinplot(x="time",y="tip",data=df)
plt.title("tip amount time of day")

```
<img width="284" alt="278807943-85c6cfba-377f-4a38-9487-a90556035ac8" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/ac01355a-5ec1-43f0-9f71-08e4258b8578">


```

sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()

```
<img width="280" alt="278807977-67b651a6-ac90-4793-8d11-b99af66067ca" src="https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-09/assets/113497037/bcc249fb-a154-41ae-90ed-ed072e63e16e">

# RESULT: 


Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.





