# Energy A.I. Hackathon 2021

## Hosts: [Prof. Michael Pyrcz](https://twitter.com/GeostatsGuy) and [Prof. John Foster](https://twitter.com/johntfoster)

### Architects: [Honggen Jo](https://twitter.com/HonggeunJ) and Mingyuan Yang

### Sponsor: [Prof. Jon Olson](https://twitter.com/ProfJEOlson), and the [Hildebrand Department of Petroleum and Geosystems Engineering](https://twitter.com/UT_PGE)

### Organization and Student Engagement: Gabby Banales and Sara Hernando

___

### Energy A.I. Problem Description 

**Goal**: develop a data analytics and machine learning workflow in Python to predict estimates and uncertainty models for cumulative oil 3 year production for 10 wells. 

#### Background

We challenge the Energy A.I. hackathon teams of The University of Texas at Austin, engineering and science Students to build a data-driven model to predict oil production. This will require:

* data analysis and evaluation of multiple data sources and a variety of features
* integration of domain expertise
* training and tuning robust machine learning prediction models
* integration and modeling of uncertainty  

This data-driven approach will replace the conventional engineering and geoscience approach:

* characterizing and modeling the subsurface
* physics-based fluid flow simulations
 
#### The Dataset Summary



![Test Image 8](https://github.com/PGEHackathon/data/blob/main/image.png)

The reservoir that we investigate in this project is roughly of the size of 10km by 10km by 50m (thickness). The initial oil water contact is at the depth of 3067.4m and the average connate water saturation is about 20.3%. 83 vertical wells were drilled across the reservoir and completed throughout the payzones. The figure above shows a top view of the reservoir as well as the location of a vertical fault that crosses the reservoir. Due to the field managements, only 73 wells were open to produce oil for the first three years, while the rest 10 wells were kept shut-in. At the end of the third year, the pre-drilled 10 wells are planned to be opened, now the question is what would be the cumulative oil productions for these 10 wells in 3 years.      

### Available data

#### wellbore_data_predrilled_wells.csv, wellbore_data_producer_wells.csv

These two files contains the well log data along the wellbore for all 83 wells. All the well names are encrypted into numbers from 1 to 83 (Well_ID). The wells from 1 to 73 are the old producer wells and the rest (74 to 83) are the pre-drilled wells of interest. The available petrophysical and geo-mechanical properties are listed and their meanings are self-explanatory. Note that the blank entries in the file indicate that the data is missing at that location.


#### 2d_ai.npy, 2d_top_depth.npy, 2d_sand_propotion.npy, 2d_sandy_shale.npy, 2d_shaly_sand.npy, 2d_shale.npy

Besides the wellbore data, there are other six datasets that are available to us. The data contained in these six files are acoustic impedance (AI), proportion of four rock facies, and top depth of the reservoir. They are collected on a regular grid (200 by 200) across the reservoir and their values indicate the vertically averaged property. The interval of measurements are 50m for both directions. The arrays in the files are provided in the format of y-x, e.g. to select the 5th grid in x and the 10th grid in y, use array[9,4] in Python or array[10,5] in Matlab. In addition, the origin of the 2D data(e.g., array[0,0]) is 25m and 25m along y and x direction in the top view horizontal map.

#### Production_history.csv

This file contains the cumulative oil and water productions for the 73 producer wells after 1 year, 2 years and 3 years.

#### Solution_template.csv

This is file which is filled with dummy values. Your submitted file should follow the same format of this file, which includes your cumulative oil production predictions and 100 prediction realizations for each pre-drilled well in 3 years. You may use what you have learnt in the short lecture to generate those realizations. 

### Submission files

* Each group should submit one .csv file which contain your predictions for the 10 pre-drilled wells. The submitted file should follow the format of the provided template.

* A compressible folder is required. It needs to contain a working .ipynd file along with all data files in your analysis which can be used to reproduce your solutions. 


```python

```
