# Ex02-Outlier

You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR 

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

    (i) Using IQR detect weight outliers and print them

    (ii) Using IQR, detect height outliers and print them
    
    
### Aim:
TO detect and remove the outliers in the given data set and save the final data.

### Algorithm:
### Step 1
Import the required packages(pandas,numpy,scipy)

### Step 2
Read the given csv file

### Step 3
Convert the file into a dataframe and get information of the data.

### Step 4
Remove the non numerical data columns using drop() method.

### Step 5
Detect the outliers in the data set using z scores method.

### Step 6
Remove the outliers by z scores and list manupilation or by using Interquartile Range(IQR)

### Step 7
Check if the outliersare removed from data set using graphical methods.

### Step 8
Save the final data set into the file.

### Program:
#### 1) & (2) Examine price_per_sqft column and use IQR to remove outliers and create new dataframe.
Program developed by : R.brindha Register number : 21222230023

import pandas as pd import numpy as np import seaborn as sns

df = pd.read_csv("/content/bhp.csv") df

df.head()

df.describe()

df.info()

df.isnull().sum()

df.shape

sns.boxplot(x="price_per_sqft",data=df)

q1 = df['price_per_sqft'].quantile(0.25) q3 = df['price_per_sqft'].quantile(0.75) print("First Quantile =",q1,"\nSecond Quantile =",q3)

IQR = q3-q1 ul = q3+1.5IQR ll = q1-1.5IQR

df1 =df[((df['price_per_sqft']>=ll)&(df['price_per_sqft']<=ul))] df1

df1.shape

sns.boxplot(x="price_per_sqft",data=df1)

### (3)Examine price_per_sqft column and use zscore of 3 to remove outliers.
from scipy import stats z = np.abs(stats.zscore(df['price_per_sqft'])) df2 = df[(z<3)] df2

print(df2.shape) sns.boxplot(x="price_per_sqft",data=df2)

### (4)(i) For the data set height_weight.csv detect weight outliers using IQR method.
df3 = pd.read_csv("height_weight.csv") df3

df3.head()

df3.info()

df3.describe()

df3.isnull().sum()

df3.shape

sns.boxplot(x="weight",data=df3)

q1 = df3['weight'].quantile(0.25) q3 = df3['weight'].quantile(0.75) print("First Quantile =",q1,"\nSecond Quantile =",q3)

IQR = q3-q1 ul = q3+1.5IQR ll = q1-1.5IQR

df4 =df3[((df3['weight']>=ll)&(df3['weight']<=ul))] df4

df4.shape

sns.boxplot(x="weight",data=df4)

### (4)(ii) For the data set height_weight.csv detect height outliers using IQR method.
sns.boxplot(x="height",data=df3) q1 = df3['height'].quantile(0.25) q3 = df3['height'].quantile(0.75) print("First Quantile =",q1,"\nSecond Quantile =",q3)

IQR = q3-q1 ul = q3+1.5IQR ll = q1-1.5IQR

df5 =df3[((df3['height']>=ll)&(df3['height']<=ul))] df5

df5.shape

sns.boxplot(x="height",data=df5)
### OUTPUT
### (1)(2) Examine price_per_sqft column and use IQR to remove outliers and create new dataframe.
### Dataset:

![sd1](https://user-images.githubusercontent.com/118708245/228194843-6b2d5d87-6dae-4bdd-aa55-cadeec88372b.png)
### Dataset Head :

![sd2](https://user-images.githubusercontent.com/118708245/228195028-18c552dd-cb0b-4dcd-ab85-4fed712f3dd1.png)
### Dataset Info :

![sd3](https://user-images.githubusercontent.com/118708245/228195417-576aac47-72f2-488e-8bd8-2f3e16135528.png)
### Dataset Describe:

![sd4](https://user-images.githubusercontent.com/118708245/228195913-070ae601-14ff-46c6-ae38-09fe97e7937c.png)
### Null Values:

![sd5](https://user-images.githubusercontent.com/118708245/228196570-e2bcf7fb-da56-420f-9fda-2b94443e1951.png)
### Dataset Shape:

![sd6](https://user-images.githubusercontent.com/118708245/228196790-79ccf449-8f0d-408d-b4c4-26a721c0d903.png)
### Box plot of price_per_sqft column with outliers:

![sd7](https://user-images.githubusercontent.com/118708245/228197048-67203d67-60eb-434f-af7b-b9f00b50b3c9.png)

### (3) Examine price_per_sqft column and use zscore of 3 to remove outliers.

![sd7](https://user-images.githubusercontent.com/118708245/228197589-58cdfaae-d9f7-4443-9dc4-aae93e224e84.png)

### Shape of Dataset after removal of outlier using z score:

![sd9](https://user-images.githubusercontent.com/118708245/228198156-34705813-efb0-4ae6-8b0b-494535c3614c.png)

### (4) For the data set height_weight.csv detect weight and height outliers using IQR method:
### Dataset:

![sd10](https://user-images.githubusercontent.com/118708245/228198397-f4031048-e2d2-49b7-85d9-e6de4f2b3ba8.png)

### Dataset Head:

![sd11](https://user-images.githubusercontent.com/118708245/228198531-b383aaa2-bee2-432f-8943-88f0093352a6.png)

### Dataset Info:

![sd12](https://user-images.githubusercontent.com/118708245/228198629-334acf8c-7e04-401c-b8ab-c0ad45eb2e3b.png)

###  Dataset Describe:

![sd13](https://user-images.githubusercontent.com/118708245/228198801-3a8fca60-5d74-4491-ac96-dbab5f4fc4fb.png)
### Null Values:
![sd14](https://user-images.githubusercontent.com/118708245/228199016-f34d7174-9f15-4d5e-a832-b8a04129454c.png)

### Dataset Shape:

![sd15](https://user-images.githubusercontent.com/118708245/228199206-4066513a-2676-43d2-96e5-dac1d388c60b.png)

### Weight - With outliers:

![sd16](https://user-images.githubusercontent.com/118708245/228199564-6d6dd0e9-5cd3-418c-879d-f1763030abe9.png)

### Weight - Dataset after removing Outliers using IQR method:

![sd17](https://user-images.githubusercontent.com/118708245/228202607-4a275746-a8d0-4044-a2bc-5e9b5eb9b054.png)

### Weight - Shape of Dataset after removing Outliers using IQR method:

![sd18](https://user-images.githubusercontent.com/118708245/228203249-ed25f198-b9aa-4582-a1fb-8d1c942e4018.png)

### Weight - Without Outliers using IQR method:

![sd19](https://user-images.githubusercontent.com/118708245/228203445-e931f48d-46a0-4274-bb30-524802832099.png)

### Height - With outliers:

![sd20](https://user-images.githubusercontent.com/118708245/228203765-37fe28e8-314d-4498-9569-017c32993564.png)

### Height - Dataset after removing Outliers using IQR method:

![sd21](https://user-images.githubusercontent.com/118708245/228203926-5e837f7a-47d5-4459-8600-37740b671ea1.png)
### Height - Shape of Dataset after removing Outliers using IQR method:

![sd22](https://user-images.githubusercontent.com/118708245/228204194-5c73c496-b690-4d20-9b14-ac36d7ec3c3d.png)

### Height - Without Outliers using IQR method:

![sd23](https://user-images.githubusercontent.com/118708245/228204510-a72401c2-0d72-4e68-8fb1-d5e414ce479f.png)

### Result:

Thus the outliers are detected and removed in the given file and the final data set is saved into the file.











