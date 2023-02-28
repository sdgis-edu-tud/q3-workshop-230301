# How to aggregate major land use classes to a grid on a regional scale in Europe?

Author: Claudiu Forgaci  
Software: QGIS 3.24.0-Tisler

## Input data

- CLC2018
- EEA grid 10x10km

All input data were reprojected to the CRS EPSG:3035.

## Steps

1. We start by dissolving the CLC2018 layer by Level 1 class. This will give us 5 classes, instead of the original 44 classes grouped in a three-level hierarchy. If a higher level of detail is desired, one can work with Level 2 or Level 3 classes. The result is a layer with five rows in the attribute table, each corresponding to a CLC Level 1 class. Use the `Vector > Geoprocessing Tools > Dissolve...` tool to dissolve the layer containing the CLC data. Select `Level 1` as the dissolving field.

2. When trying to run the tool in step 1, it is likely that the CLC layer has invalid geometries and throws an error. Steps to overcome that issue:

    1.a. To check if the layer has invalid geometries, run the `Check validity` too from the processing toolbox with the `GEOS` method selected. The tool generates three layers: `Valid output`, `Invalid output`, and `Error output`. `Invalid output` and `Error output` will show the invalid geometry and describe the type of error, respectively.

    1.b. Use the `Fix geometries` tool from the processing toolbox with the CLC layer as input and either create a temporary file or save the resulted layer as a separate shapefile in your file system.

    1.c. Re-run the dissolve operation using the layer with fixed geometries as input.

3. Intersect the dissolved layer with the grid layer.

4. Generate points from the polygons with `Vector > Geometry Tools > Polygon Centroids...`.

5. Join the points to the original grid with `Data Management Tools > Join Attributes by Location...`.  
