# Energy A.I. Hackathon 2021

## Hosts: [Prof. Michael Pyrcz](https://twitter.com/GeostatsGuy) and [Prof. John Foster](https://twitter.com/johntfoster)

### Architects: [Honggen Jo](https://twitter.com/HonggeunJ) and Mingyuan Yang

### Sponsor: [Prof. Jon Olson](https://twitter.com/ProfJEOlson), and the [Hildebrand Department of Petroleum and Geosystems Engineering](https://twitter.com/UT_PGE)

### Organization and Student Engagement: Gabby Banales and Sara Hernando

___

### Energy A.I. Problem Description 

**Goal**: develop a data analytics and machine learning workflow in Python to predict estimates and uncertainty models for cumulative oil 3 year production for **10 unproduced wells**. 

#### Background

We challenge the Energy A.I. hackathon teams of The University of Texas at Austin, engineering and science Students to build a data-driven model to predict oil production. This will require:

* data analysis and evaluation of multiple data sources and a variety of features
* integration of domain expertise
* training and tuning robust machine learning prediction models
* integration and modeling of uncertainty  

This data-driven approach will replace the conventional engineering and geoscience approach:

* characterizing and modeling the subsurface
* physics-based fluid flow simulations

___
 
#### The Reservoir Unit

Specifications of the reservoir unit of interest: 

* **Depositional Setting**: clastic deepwater reservoir unit with extents 10km by 10km by 50m (thickness)
* **Fluids**: initial oil water contact is at the depth of 3067.4m and the average connate water saturation is about 20.3%
* **Structure**: Anticline structure with a major vertical fault that crosses the reservoir. 

![Test Image 8](https://github.com/PGEHackathon/data/blob/main/image.png)

* **Wells**: 83 vertical wells were drilled across the reservoir and completed throughout the payzones. Due to the field managements, only 73 wells were open to produce oil for the first three years, while the remaining 10 wells were kept shut-in. At the end of the third year, the remaining 10 unproduced wells are planned to be openned.

* **Question**: What will be the the cumulative oil production for each of these 10 unproduced wells over the next 3 years?  

___

### Available Data Files Inventory

You have the following data files.

#### wellbore_data_preproduction_wells.csv, wellbore_data_producer_wells.csv

These two files contain the well log data along the wellbore for all 83 wells. All the well names are encrypted into numbers from 1 to 83 (Well_ID). The wells from 1 to 73 are the old producer wells and the remainder (74 to 83) are the pre-produced wells of interest (that you will predict). The available petrophysical and geo-mechanical properties are listed. Note that the blank entries in the file indicate missing data at those locations.

#### 2d_ai.npy, 2d_top_depth.npy, 2d_sand_propotion.npy, 2d_sandy_shale.npy, 2d_shaly_sand.npy, 2d_shale.npy

Besides the wellbore data, there are other six datasets that are available to us. The data contained in these six files are acoustic impedance (AI), proportion of four rock facies, and top depth of the reservoir. They are collected on a regular grid (200 by 200) across the reservoir and their values indicate the vertically averaged property. The interval of measurements are 50m for both directions. The arrays in the files are provided in the format of y-x, e.g. to select the 5th grid in x and the 10th grid in y, use array[9,4] in Python or array[10,5] in Matlab. In addition, the origin of the 2D data(e.g., array[0,0]) is 25m and 25m along y and x direction in the top view horizontal map.

#### Production_history.csv

This file contains the cumulative oil and water productions for the 73 producer wells after 1 year, 2 years and 3 years.

___

The following file are available to assist with developing the products for submission.

#### Solution_template.csv

A solution templay file filled with dummy values. 

* Your submitted file should follow the same format of this file, which includes your cumulative oil production predictions and 100 prediction realizations for each pre-drilled well in 3 years. You may use what you have learnt in the short lecture to generate those realizations. 

### Submission files

* Each group should submit one .csv file which contain your predictions for the 10 pre-drilled wells. The submitted file should follow the format of the provided template.

* A compressible folder is required. It needs to contain a working .ipynb file along with all data files in your analysis which can be used to reproduce your solutions. 


```python

```
