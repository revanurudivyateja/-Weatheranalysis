Ex:10 Data Science Process on Complex Dataset

AIM:
To Perform Data Science Process on a complex dataset and save the data to a file. 

ALGORITHM:

STEP 1 Read the given Data.
STEP 2 Clean the Data Set using Data Cleaning Process.
STEP 3 Apply Feature Generation/Feature Selection Techniques on the data set.
STEP 4 Apply EDA /Data visualization techniques to all the features of the data set.

PROGRAM:
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import io
from google.colab import files

# Upload the 'FlightInformation.csv' file
uploaded = files.upload()

# Read the CSV file
dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv']))

# Print the contents of the DataFrame
print(dd)

sns.barplot (x=dd['Duration'],y=dd['Price'])

sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)

states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()

dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()

```
OUTPUT:

DATA
![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/818afcdf-9bd6-4030-826c-9f4096fae267)

![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/59890bc2-692e-4ddd-80fc-15370f10af9f)


![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/f13d3bdb-caf1-432c-939d-c610f877e53b)

```
The data to be plotted:

[[11 23 46 91 90 57 86 49 40 93]
 [88 49 66 90 40 78 24 73 17 68]
 [31 92 95 95 29 35 20 63 49 86]
 [75 59 99 94 56 79 30 40  8 89]
 [41  9 40 15 95 88 78 30 49 69]
 [10 84 20 95 18 92 24 36 92 42]
 [97 24 73 52 84 17 59 36 68 24]
 [ 5  1 88 54 29 61 68  5 80 30]
 [49 38 43 12 78 35 72 75 29 38]
 [35 53 63 63 26 66 79 61 32 57]]
```

![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/9b46f476-4d3d-4a71-8398-3a77b2ecaa89)


