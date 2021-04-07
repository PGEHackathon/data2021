```python
import numpy as np
import pandas as pd
```

## Hackathon competition

### Problem description 

This competition challenges data scientists to make predictions of future oil production from various data sources taken from a hydrocarbon reservoir and wells. Unlike the conventional approach (e.g., characterizing reservoir models, running fluid flow simulations, and quantifying the uncertainty), you'll use machine learning techniques to discover the relations within the available data and quatities of interest.

![image.png](attachment:c9aec0ea-da07-4c02-9976-ee0547b8247f.png)

The reservoir that we investigate in this project is roughly of the size of 10km by 10km by 50m (thickness). The initial oil water contact is at the depth of 3067.4m and the average connate water saturation is about 20.3%. 83 vertical wells were drilled across the reservoir and completed throughout the payzones. The figure above shows a top view of the reservoir as well as the location of a vertical fault that crosses the reservoir. Due to the field managements, only 73 wells were open to produce oil for the first three years, while the rest 10 wells were kept shut-in. At the end of the third year, the pre-drilled 10 wells are planned to be opened, now the question is what would be the oil productions for these 10 wells in next 1 year, 2 years and 3 years.      

### Available data

#### wellbore_data.csv

This file contains the well log data along the wellbore for all 83 wells. All the well names are encrypted into numbers from 1 to 83 (Well_ID). The wells from 1 to 73 are the old producer wells and the rest (74 to 83) are the pre-drilled wells of interest. The available petrophysical and geo-mechanical properties are listed and their meanings are self-explanatory. Note that the blank entries in the file indicate that the data is missing at that location.


#### 2d_ai.npy, 2d_facies.npy, 2d_top_depth.npy

Besides the wellbore data, there are other three datasets that are available to us. The data contained in these three files are acoustic impedance (AI), proportion of rock facies, and top depth of the reservoir. They are collected on a regular grid (200 by 200) across the reservoir and their values indicate the vertically averaged property. The interval of measurements are 50m for both directions. The arrays in the files are provided in the format of y-x.

Note that the rock facies file contains an array of 4 by 200 by 200 which corresponds to 4 different rock types percentages in the formation. They are as follow,

* 1 Shale 
* 2 Sandy shale 
* 3 Sandstone 
* 4 Shaly sandstone 

#### Production_history.csv

This file contains the cumulative oil and water productions for the 73 producer wells after 1 year, 2 years and 3 years

#### Solution_template.csv

---not finished here, should be production prediction and 50 realizations, something like this, explain what they are, and what the realization means.


```python
tmp_list = ['Well_no_' + str(i+74) for i in range(10)]
np.random.seed(10)
tmp_array = np.random.rand(10, 11)
df1 = pd.DataFrame(tmp_array)
data = {'Well_ID' : tmp_list}
df = pd.DataFrame(data)
df2 = pd.concat([df, df1], axis=1)
df2.rename(columns={0:'Prediction, MSTB'}, inplace=True)
for i in range(10):
    df2.rename(columns={i+1:'R'+str(i+1)+', MSTB'}, inplace=True)

df2.insert(1,'Production time, year', 1)

df3 = pd.concat([df2, df2, df2], ignore_index=True)

df3.loc[10:20, 'Production time, year'] = 2
df3.loc[20:,'Production time, year'] = 3
    
print (df3.shape)
```

    (30, 13)



```python
df3.to_csv('solution_template.csv', index=False)
```

### Submission files

* Each group should submit one .csv file which contain oil production predictions from the 10 wells in 1 year, 2 year and 3 years. The submitted file should follow the format of the provided template.

* A compressible folder is required. It needs to contain a working .ipynd file along with all data files in your analysis which can be used to reproduce your solutions. 


```python

```
