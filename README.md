# Santarém: Temporal Analysis of Landsat and Sentinel Data in the Santarém Region

### Description

This repository contains code for the temporal analysis of Landsat and Sentinel satellite images in the Santarém region. The scripts have been written using the Google Earth Engine API and include functionalities for:

- Importing shapefiles containing study areas.
- Filtering and classifying Landsat and Sentinel images for multiple years.
- Calculating vegetation indices (NDVI) and water indices (NDWI).
- Land use classification using Random Forest.

### Prerequisites

To use this project, you'll need:

- A Google Earth Engine account.
- The Google Earth Engine API installed.

### Repository Structure

- **loop-landsat-indices**: Script for analysis using Landsat data.
- **loop-sentinel-indices**: Script for analysis using Sentinel data.
- **selecaoImagemSemNuvem**: Script with a draft of how cloud-free image selection was performed.

### How to Use

1. Access Google Earth Engine and paste the code from each loop file into separate files.
2. Open the Google Earth Engine Script Editor and paste the code.
3. Download the polygons to the Assets folder of your GEE project.
4. Rename the file paths correctly in:

   ```javascript
   var shapefile = ee.FeatureCollection("...");
   var geometryCollection = ee.FeatureCollection("...");
   ```

5. Execute the script.

Click the 'Run' button to execute the script.

### Script Features

- **Shapefile Import**: Imports shapefiles that define the study area in Santarém.
- **Temporal Loop**: Loops to filter and collect images for multiple years.
- **Index Calculation**: Functions to calculate NDVI and NDWI depending on the Landsat sensor.
- **Random Forest Classifier**: Implementation of the Random Forest classification.

Each image is categorized (classified) individually using the training polygons. Each image is first clipped to the study area's polygon (shapefile). Then, NDVI and NDWI indices are calculated for each image. Training data is collected from the polygons of interest (geometryCollection), and a Random Forest classifier is trained with this data. Finally, each image is classified using the trained classifier and added to the map.
