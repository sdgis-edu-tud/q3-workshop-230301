# What is the spatial distribution of city sizes in North-West Europe?

Author: Claudiu Forgaci  
Software: QGIS 3.24.0-Tisler

## Input data

- [Urban Audit point data](https://ec.europa.eu/eurostat/web/gisco/geodata/reference-data/administrative-units-statistical-units/urban-audit#ua20) with the location of cities and greater cities in SHP format
- [Eurostat population data for cities and greater cities](https://ec.europa.eu/eurostat/web/cities/data/database) in wide (time-series) format (non-spatial)

All spatial input data were reprojected to the CRS EPSG:3035.

## Spatial extent  

Bounding box coordinates (Format: Lng / Lat, GDAL):  
3500000.0000000000000000,2680000.0000000000000000 : 4490000.0000000000000000,3670000.0000000000000000

## Steps

1. Import the Urban Audit point data to QGIS. From the downloaded archive, use the `URAU_LB_2021_3035_CITIES.shp` shapefile 

2. Import the population data via `Data Sourcer Manager > Delimited Text`. Browse for the population file downloaded in CSV format from Eurostat. Set `Geometry Definition` to `No geometry (attribute only table)`. If the sample data preview looks correct, click on add. The data will be loaded as a non-spatial layer in QGIS.

3. 