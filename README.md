# README: Exercise 4 - Cartography

## Overview
This project focuses on using Altair for rendering maps and applying color scales to visualize geospatial data. It includes multiple choropleth maps depicting various home sales statistics in Chicago and Houston. The goal is to understand cartographic visualization techniques and practice different encoding strategies.

## Data Sources
The following datasets were used:

1. **Chicago Ward Boundaries (2015-2023)** - GeoJSON file containing the historical ward boundaries of Chicago.
   - Source: [City of Chicago Open Data Portal](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Wards-2015-2023-/sp34-6z76)
   
2. **Chicago Home Sales Data (2020-2021)** - CSV file containing home sales statistics for different types of properties.
   - Source: [Tableau Public Dataset](https://public.tableau.com/app/profile/ccao/viz/DataChicagoHomes/WardMap)
   
3. **Houston Neighborhood Boundaries** - GeoJSON file of Houston's super neighborhoods.
   - Source: [City of Houston GIS Open Data](https://cohgis-mycity.opendata.arcgis.com/datasets/deae15e7f3db4b198946c17f0d169c39_3/explore?location=29.822644%2C-95.415250%2C10.18)
   
4. **Houston Home Prices** - Median home prices by super neighborhood in Houston.
   - Source: [Houston Planning and Development](https://www.houstontx.gov/planning/Demographics/docs_pdfs/SN/Median_Housing_Value_by_SN.pdf)

## Chicago Ward Maps

### 1. Ward Map
- A simple map of Chicago's wards was created using a **Mercator projection** to accurately represent geographic boundaries.
- A tooltip displays the ward number when hovering over each region.

### 2. Most Sold Property Type (2020)
- A choropleth map was created to display the **most frequently sold home type per ward**.
- The colors were selected to be distinct and colorblind-friendly:
  - **Single-Family Homes:** Blue (#377eb8)
  - **Multi-Family (2-6 units):** Red (#e41a1c)
  - **Condos:** Yellow (#ffbf00)
- A black border outlines the wards for improved visibility.

### 3. Median Home Prices by Property Type
- Three separate choropleth maps were created to show **median home prices** for:
  - Single-Family Homes
  - Multi-Family (2-6 units)
  - Condos
- A **single-hue blue color scale** was used, as home prices are quantitative values.
- The same scale was applied to all three maps for consistent comparisons.

### 4. Ratio of Single-Family to Condo Sales
- A choropleth map was created to show the **log ratio** of single-family home sales to condo sales.
- **A diverging red-blue color scale** was used:
  - **Blue:** Higher single-family sales
  - **Red:** Higher condo sales
  - **Gray (Middle = 0):** Equal sales
- Log transformation was applied to normalize extreme values, and infinite ratios were capped at the largest finite ratio.

## Houston Neighborhood Maps

### 1. Median Home Prices in Houston
- A choropleth map of Houston neighborhoods displaying **median home prices**.
- A **log transformation** was applied to prices to account for large disparities between neighborhoods.
- A **single-hue blue scale** was used for the visualization.
- The **Identity projection** was used due to limitations with Mercator projection in the dataset.

## Installation & Requirements
This project requires:
- Python 3.x
- Pandas
- Altair
- NumPy
- GeoJSON (for loading geographic data)

To install dependencies:
```sh
pip install pandas altair numpy geojson
```

## Running the Notebook
Open the Jupyter Notebook and execute the cells in sequence. Ensure that all necessary files (Chicago wards GeoJSON, Houston neighborhoods GeoJSON, and home sales CSV files) are in the working directory.

## Key Learnings
- How to create **choropleth maps** with **Altair**.
- How to use **different color scales** based on the type of data (nominal vs. quantitative vs. diverging).
- How to apply **geospatial transformations** to correct coordinate issues.
- How to handle **missing values and infinite ratios** in data preprocessing.

## Future Improvements
- Improve **projection accuracy** for Houston’s map.
- Overlay additional **point data** to enhance visualizations.
- Implement **interactive filtering** for better data exploration.

