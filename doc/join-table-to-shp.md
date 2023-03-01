# What is the spatial distribution of population sizes in large cities of North-West Europe?

Author: Claudiu Forgaci  
Software: QGIS 3.24.0-Tisler

## Input data

- [Urban Audit point data](https://ec.europa.eu/eurostat/web/gisco/geodata/reference-data/administrative-units-statistical-units/urban-audit#ua20) with the location of cities and greater cities in SHP format
- [Eurostat population data for cities and greater cities](https://ec.europa.eu/eurostat/web/cities/data/database) in wide (time-series) format (non-spatial)

All spatial input data were available in or reprojected to the CRS EPSG:3035.

## Spatial extent  

Bounding box coordinates (Format: Lng / Lat, GDAL):  
3500000.0000000000000000,2680000.0000000000000000 : 4490000.0000000000000000,3670000.0000000000000000

## Steps

1. Import the Urban Audit point data to QGIS. From the downloaded archive, use the `URAU_LB_2021_3035_CITIES.shp` shapefile or a clipped version of it if you are interested in a specific region of the EU. For North-West Europe, we use the points that fall within the spatial extent specified above.

2. Import the population data via `Data Sourcer Manager > Delimited Text`. Browse for the population file downloaded in CSV format from Eurostat. Set `Geometry Definition` to `No geometry (attribute only table)`. If the sample data preview looks correct, click on add. The data will be loaded as a non-spatial layer in QGIS.

3. In the properties of the `URAU_LB_2021_3035_CITIES` layer, go to the `Joins` tab. Click on `+` to create a join. Set the join layer to the imported table with population data. Make sure the fields (columns) contaning the URAU code from both the shapefile and the table are set as the `Join field` and `Target field`, respectively. Optionally, set `Custom field prefix` to `pop_`; that way the joined fields will be formatted as `pop_YEAR`, which is especially useful when multiple time-series variables are imported in the same table.  
