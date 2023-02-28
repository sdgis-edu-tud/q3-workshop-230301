# What is the spatial distribution of road network density on a regional scale in North-West Europe?

Author: Claudiu Forgaci  
Software: QGIS 3.24.0-Tisler

## Input data

- OSM data with Key: `highway` and Values: `primary`, `primary_link`, `secondary`, `secondary_link`, `tertiary`, `tertiary_link`, `motorway`, `motorway_link`  
- EEA grid 10x10km  

All input data were reprojected to the CRS EPSG:3035.

## Spatial extent  

Bounding box coordinates (Format: Lng / Lat, GDAL):  
3500000.0000000000000000,2680000.0000000000000000 : 4490000.0000000000000000,3670000.0000000000000000

## Steps

1. Use the processing tool `Vector > Analysis Tools > Sum line lengths...` to calculate the total length of roads in each cell.  

2. The newly created field can be used to visualised road density. Use natural breaks when visualising the new `LENGTH` column.
