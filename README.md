Ex:10 Data Science Process on Complex Dataset

AIM:
To Perform Data Science Process on a complex dataset and save the data to a file. 

ALGORITHM:
```
STEP 1 Read the given Data.
STEP 2 Clean the Data Set using Data Cleaning Process.
STEP 3 Apply Feature Generation/Feature Selection Techniques on the data set.
STEP 4 Apply EDA /Data visualization techniques to all the features of the data set.
```
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
```
executed in the current browser session. Please rerun this cell to enable.
Saving FlightInformation.csv to FlightInformation.csv
           Airline Date_of_Journey    Source Destination  \
0           IndiGo      24/03/2019  Banglore   New Delhi   
1        Air India       1/05/2019   Kolkata    Banglore   
2      Jet Airways       9/06/2019     Delhi      Cochin   
3           IndiGo      12/05/2019   Kolkata    Banglore   
4           IndiGo      01/03/2019  Banglore   New Delhi   
...            ...             ...       ...         ...   
10678     Air Asia       9/04/2019   Kolkata    Banglore   
10679    Air India      27/04/2019   Kolkata    Banglore   
10680  Jet Airways      27/04/2019  Banglore       Delhi   
10681      Vistara      01/03/2019  Banglore   New Delhi   
10682    Air India       9/05/2019     Delhi      Cochin   

                       Route Dep_Time  Arrival_Time Duration Total_Stops  \
0                  BLR → DEL    22:20  01:10 22 Mar   2h 50m    non-stop   
1      CCU → IXR → BBI → BLR    05:50         13:15   7h 25m     2 stops   
2      DEL → LKO → BOM → COK    09:25  04:25 10 Jun      19h     2 stops   
3            CCU → NAG → BLR    18:05         23:30   5h 25m      1 stop   
4            BLR → NAG → DEL    16:50         21:35   4h 45m      1 stop   
...                      ...      ...           ...      ...         ...   
10678              CCU → BLR    19:55         22:25   2h 30m    non-stop   
10679              CCU → BLR    20:45         23:20   2h 35m    non-stop   
10680              BLR → DEL    08:20         11:20       3h    non-stop   
10681              BLR → DEL    11:30         14:10   2h 40m    non-stop   
10682  DEL → GOI → BOM → COK    10:55         19:15   8h 20m     2 stops   

      Additional_Info  Price  
0             No info   3897  
1             No info   7662  
2             No info  13882  
3             No info   6218  
4             No info  13302  
...               ...    ...  
10678         No info   4107  
10679         No info   4145  
10680         No info   7229  
10681         No info  12648  
10682         No info  11753  

[10683 rows x 11 columns]
```

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
RESULT:

Hence Data Science Process on Complex Dataset  successfully completed program

