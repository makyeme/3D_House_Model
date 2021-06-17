# 3D_House_Model


## Table of contents
* [GeneralInformation](#generalinformation)
* [Technologies](#technologies)
* [Setup](#setup)
* [Status](#status)



## General Information

In this project,  geospatial data obtained by the LIDAR method was used to develop a 3D Model of a house.
The 3D model is generated and plotted by inputting a simple home address. 
LIDAR measures distance using light. The target is illuminated by a laser light, a sensor will then detect and measure the reflection off the target. Differences in wavelength and return times are used to obatain the 3D representations of an area.


The ***code for this project can be viewed/obtained*** at [CODE](https://github.com/makyeme/Test/blob/main/3D_House_Final.ipynb)


## Technology

This project was created with:

* Anaconda virtual environment(Geodata)  version: 4.9.2
* anaconda-navigator version: 1.10.0
* Python version: 3.8.5
* Jupyter notebook version: 6.2.0
* Numpy library version: 1.19.2
* Requests version: 2.25.1
* Matplotlib library version: 3.3.4
* Rasterio library version: 1.9.0
* Json5 library version: 0.9.5
* Geopandas library version: 0.8.1
* Pandas library version: 1.2.1
* gdal library version: 3.0.2
* Plotly Library version: 4.14.3


## Setup

![Optional Text](https://github.com/makyeme/3D_House_Model/blob/main/3D_images/CHM.png)

Visualization of the Canopy Height Model-generating process


#### 1. Exploring the raster Images

- In this code segment, I explore the **Digtal Surface Model(DSM)** and the **Digtal Terrain Model(DTM)**.
  - A ***DSM*** represents the elevations of the reflective surfaces of trees, buildings, and other features elevated above the “Bare Earth”
  - A ***DTM*** is a topographic model of the bare Earth that can be manipulated by computer programs

- Useful information on the raster images is generated, such as :

    - Image bounds, 
    - Coordinate refrence system (crs)
    - Displaying image array
    - Images of the untransformed and transformed rasters are displayed
    - Libraries used: numpy, matplotlib, gdal, rasterio

#### 2. Obtaining the Canopy Hieght Model (CHM)

   - ***CHM*** is the residual value or difference between the top of the earth surface and the ground which should be the heights of the trees
   - Under this code segment, the ***CHM*** is generated by subtracting ***DTM*** array from the ***DSM*** array
   - A 2D plot of the CHM is generated for visual exploration
   - The created raster of the CHM is exported to a target local directory
   - Libraries used: numpy, matplotlib, gdal, rasterio

#### 3. Generating polygon of input home address
- Under this code segment:
    - From the API: basisregisters.vlaanderen.be
    - I use the requests & Json libraries to obtain polygon coordinates of input home address 
    - The polygon request is executed in three steps
    - The generated polygon shapefile is exported to target directory
    - Libraries used: requests, json, geopandas

#### 4. Plotting the polygon of input home address
    - Libraries used: requests, json, geopandas, matplotlib

#### 5. Musking and clipping CHM raster using polygon of home address
   - In this code segment, I generate a clipped raster of the CHM
   - and store it in a target directory
   - Libraries used: rasterio

#### 6. Generating 3D plot of the input home address
  - In this code segment, 3D plots of home adress are generated
  - First I use the matplotlib library (several formarts of plots are displayed)
  - Then I use the Plotly library 
  


| Line plot                        | Contour plot                                    | Scatter plot                            | Plotly |
| ------------------------------------- | ------------------------------------------ | ---------------------------------------- | --------------------- |
| ![Line](https://github.com/makyeme/3D_House_Model/blob/main/3D_images/line_plot.PNG) | ![Contour](https://github.com/makyeme/3D_House_Model/blob/main/3D_images/contour_plot.PNG) | ![Scatter](https://github.com/makyeme/3D_House_Model/blob/main/3D_images/scatter_plot.PNG) | ![Plotly](https://github.com/makyeme/3D_House_Model/blob/main/3D_images/plotly_sketch.PNG)

Sample plots of the 3D house model


## Status

#### Realised 
* Obtained a 3D model of a house with only an input home address
* Better visualization 

#### Pending
* ‘Good to have features’ which incorporate house area(m²), number of rooms, surrounding features etc.
* Rapid return of search results 

 

