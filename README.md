#Ex:10 Data Science Process on Complex Dataset

##AIM:
To Perform Data Science Process on a complex dataset and save the data to a file. 

##ALGORITHM:

STEP 1 Read the given Data.
STEP 2 Clean the Data Set using Data Cleaning Process.
STEP 3 Apply Feature Generation/Feature Selection Techniques on the data set.
STEP 4 Apply EDA /Data visualization techniques to all the features of the data set.

##PROGRAM:
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
##OUTPUT:
##DATA
![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/818afcdf-9bd6-4030-826c-9f4096fae267)

![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/59890bc2-692e-4ddd-80fc-15370f10af9f)

![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/f13d3bdb-caf1-432c-939d-c610f877e53b)




![download](https://github.com/revanurudivyateja/EXPNO10/assets/129148660/9b46f476-4d3d-4a71-8398-3a77b2ecaa89)


