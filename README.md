# Copernicus Analysis Geospatial Data

Deforestation Analysis in Ross-Bethio, Senegal
==============================================

Overview
--------
This notebook analyzes deforestation in Ross-Bethio, Senegal, using satellite imagery from the Sentinel-2 satellites, part of the European Union's Copernicus Earth observation program. The analysis utilizes cloud-filtered NDVI (Normalized Difference Vegetation Index) calculations to distinguish between forested and deforested areas, offering insights into the trends and changes in forest cover from 2018 to 2024.

About Copernicus and the Sentinel Satellites
--------------------------------------------
**Copernicus** is the European Union's Earth observation program aimed at providing accurate and timely data to improve environmental management, understand climate change, and ensure civil security. Managed by the European Commission in partnership with the European Space Agency (ESA) and other organizations, Copernicus combines satellite and ground-based data to monitor various aspects of the Earth's systems, including the atmosphere, oceans, and land surfaces.

The **Sentinel** series of satellites are the cornerstone of the Copernicus program. They provide a wealth of data across multiple domains:

- **Sentinel-1**: Offers radar imaging capabilities for monitoring sea ice, tracking oil spills, and assessing land surface changes.
- **Sentinel-2**: Captures high-resolution optical imagery in multiple spectral bands, which is crucial for land monitoring, including vegetation health, soil, water bodies, and changes in land use. The imagery used in this notebook comes from Sentinel-2, making it particularly suitable for deforestation analysis.
- **Sentinel-3**: Focuses on sea and land surface temperature, ocean color, and land color monitoring, contributing to climate change studies and environmental management.
- **Sentinel-4 and Sentinel-5**: Designed for atmospheric monitoring, tracking air quality, ozone levels, and solar radiation.
- **Sentinel-6**: Dedicated to high-precision measurements of sea-level rise, aiding in the study of ocean circulation and coastal erosion.

The **Sentinel-2** satellites, specifically used in this analysis, provide multispectral imagery with high spatial and temporal resolution, allowing for frequent and detailed observations of Earth's surface. This data is vital for applications such as deforestation analysis, agricultural monitoring, disaster management, and environmental protection.

Prerequisites
-------------
- Python 3.x
- Libraries:
  - ipyleaflet
  - sentinelhub
  - requests
  - matplotlib
  - numpy
  - xarray
  - rioxarray
  - sklearn
- Sentinel Hub API credentials (client ID and client secret)

Setup and Authentication
------------------------
1. Install the required Python libraries:
2. Set up Sentinel Hub credentials:
- Obtain a `client_id` and `client_secret` from the Sentinel Hub.
- Replace the placeholders in the notebook with your own credentials to authenticate and access the Sentinel-2 imagery.

Notebook Structure
------------------
### 1. Authentication and Initial Setup
- Installs required libraries and sets up Sentinel Hub API authentication.
- Defines the area of interest (Ross-Bethio, Senegal) using geographical coordinates.
- Displays the area on a map using `ipyleaflet`.

### 2. Data Acquisition
- Uses Sentinel Hub to fetch cloud-filtered satellite imagery.
- JavaScript code is used to process images and calculate NDVI for vegetation analysis.

### 3. Data Request and Download
- Creates data requests for Sentinel-2 imagery from 2018 to 2024.
- Downloads the data using Sentinel Hub API and saves it for further analysis.

### 4. Data Processing and Visualization
- Uses `xarray` and `rioxarray` to process the downloaded geospatial data.
- Adds a time dimension to the dataset to analyze changes over the years.
- Plots the NDVI values to visualize vegetation changes in Ross-Bethio.

### 5. Forest Classification and Change Detection
- Classifies forested areas based on NDVI values.
- Calculates and visualizes forest cover and changes (gain or loss) over time.
- Provides cumulative forest loss statistics for the analyzed period.

Usage
-----
1. Run the notebook step-by-step to authenticate, download, and process the satellite data.
2. Adjust the geographical coordinates (`bbox_coords`) if analyzing a different area.
3. Modify the time interval in the `interval_of_interest` function to focus on other periods.
4. Use the visualizations to assess deforestation trends and patterns in Ross-Bethio.

Results
-------
The analysis provides:
- Yearly NDVI plots to assess vegetation health.
- True-color images of Ross-Bethio for visual reference.
- Forest classification maps to identify deforested areas.
- Cumulative forest loss graphs to understand deforestation trends.

Notes
-----
- Ensure you have the necessary permissions and credentials to access Sentinel Hub services.
- The notebook uses a custom JavaScript script for cloud filtering, focusing on obtaining clearer imagery for analysis.

License
-------
This analysis is provided for educational and research purposes. Ensure compliance with Sentinel Hub's terms and conditions when using their services.


