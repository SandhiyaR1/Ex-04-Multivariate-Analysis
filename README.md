# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

# EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8
Save the final data set into the file

# PROGRAM:
### Developed by: Sandhiya R
#### Registration Number:212221230129
### Multivariate EDA - SuperStore.csv
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df.head(6)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
sns.scatterplot (df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sns.barplot(df['Postal Code'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT
### SuperStore.csv
### df.head()
![image](https://user-images.githubusercontent.com/113497571/230001111-b2cbbea3-5b4f-4b8c-89fc-8d805e8561d4.png)


### df.info()
![image](https://user-images.githubusercontent.com/113497571/229999451-47ed1358-755e-4c17-b58c-e58fcd547ac0.png)

### df.describe()
![image](https://user-images.githubusercontent.com/113497571/230001273-7cd46dd4-d311-474f-bb89-b1ad76f01e2c.png)

### df.isnull().sum()
![image](https://user-images.githubusercontent.com/113497571/230001353-8f39750d-24b1-4ed8-a1c4-a3b026648123.png)
### AFTER CLEANING 
### df.isnull().sum()
![image](https://user-images.githubusercontent.com/113497571/230001426-a44d4df8-bc1a-41fd-b9f7-fe04b27671e2.png)

### Scatterplot
![image](https://user-images.githubusercontent.com/113497571/230001598-c62c77fa-be47-42db-972e-e42a8ecc4ae5.png)


### Barplot
![image](https://user-images.githubusercontent.com/113497571/230001681-134c8e0d-5e71-4964-bea7-c986a80bf62c.png)
![image](https://user-images.githubusercontent.com/113497571/230001759-72af43b8-09df-4705-8465-2180333572cb.png)
![image](https://user-images.githubusercontent.com/113497571/230001823-780d0089-860f-480e-b68d-63c33c7cb898.png)


###  HeatMap
![image](https://user-images.githubusercontent.com/113497571/230001875-31515270-132c-48dd-a8dc-29ab5eabd01f.png)


# RESULT
Thus the program to perform EDA on the given data set is successfully executed.
