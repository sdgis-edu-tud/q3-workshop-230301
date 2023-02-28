# What is the spatial distribution of pollution in North-West Europe?

Author: Claudiu Forgaci  
Software: QGIS 3.24.0-Tisler

## Input data

- EPRTR point data with facilities and pollutants  
- EEA grid 10x10km  

All input data were reprojected to the CRS EPSG:3035.

## Spatial extent  

Bounding box coordinates (Format: Lng / Lat, GDAL):  
3500000.0000000000000000,2680000.0000000000000000 : 4490000.0000000000000000,3670000.0000000000000000

## Steps

1. Before carrying out the analysis, make sure to run `Data Management Tools > Create Spatial Index...` on both layers. That will speed up computation time in the next step.

2. Search for the `Join Attirbutes by Location (summary)...` tool in the processing toolbox. `Join to features in` the grid layer and `By comparing to` the EPRTR points layer. Select a summary statistic to be calculated, such as `max`. You can optionally select a subset of `Fields to add` from the EPRTR layer. You can select, for instance, the `TotalQuant` column and `max` as the summary to calculate. This process will add a new column for each selected statistic and field.
