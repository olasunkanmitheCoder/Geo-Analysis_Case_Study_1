# GEOSPATIAL ASSESSMENT OF LAND COVER CHANGE AND ITS EFFECTS ON HYDROLOGICAL HAZARDS IN AKURE SOUTH, ONDO STATE, NIGERIA.

## Project Overview
This project analyzes how land cover changes influences flood and soil erosion risks in Akure South, Ondo State, Nigeria. Using satellite imagery and geospatial analysis techniques, the study evaluates land cover changes over time and models hydrological hazards such as flooding and soil erosion.
The project integrates remote sensing, GIS-based multi-criteria analysis, and hydrological modeling to identify high-risk zones and estimate the population exposed to these hazards.

## Problem Statement

Rapid land cover changes often alters natural landscapes, reducing vegetation cover and increasing impervious surfaces. These changes can intensify hydrological hazards such as flooding and soil erosion.

This project investigates:
- How land use/land cover has changed between 1990 and 2025
- Areas most susceptible to flooding and soil erosion
- The population exposed to these hazards

The goal is to provide insights that can support urban planning, environmental management, and disaster risk mitigation.

## STUDY AREA MAP
![STUDY AREA](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/Akure_South_Area_Map.jpg)

## Data Source
*Table 1*
| Data                          | Source                         | Resolution    |
| ----------------------------- | ------------------------------ | ------------- |
| Landsat TM, ETM+, OLI imagery | [USGS](https://earthexplorer.usgs.gov/)                           | 30m           |
| Digital Elevation Model (DEM) | SRTM / USGS                    | 30m           |
| Rainfall Data                 | [TAMSAT](https://data.tamsat.org.uk/)                         | 0.5°          |
| Soil Data                     | [Harmonized World Soil Database](https://iiasa.ac.at/models-tools-data/hwsd) | 30 arc-second |
| Population Density            | [WorldPop](https://hub.worldpop.org/project/categories?id=3)                       | ~1km          |

## Methodology
The workflow involved:

### Land Cover Classification and Change Detection
- Landsat imagery (1990, 2002, 2015, 2025)
- Supervised classification using Maximum Likelihood algorithm.
- Four classes identified:
    -  Built-up Area
    -  Dense vegetation
    -  Sparse vegetation
    -  Bare land/Rock OutCrop
- Post-classification comparison was used to identify changes in land cover between different years.
The analysis evaluated land cover transitions across three intervals:
  - 1990 – 2002
  - 2002 – 2015
  - 2015 – 2025

### Flood Hazard Modeling and Weighting with Analytical Hierarchy Process (AHP)
Flood susceptibility was evaluated using a GIS-based Multi-Criteria Decision Analysis (MCDA) framework. AHP was used to assign weights to flood-driving factors based on their influence on flooding. Weighted layers were combined using weighted overlay analysis to generate the final flood hazard map.

Factors used:
  - Slope
  - Elevation
  - Rainfall
  - Flow accumulation
  - Drainage density
  - Soil type
  - Land use
  - Topographic Wetness Index

Flood Hazard categorizes:
  - Very High
  - High
  - Low
  - Very Low

### Soil Erosion Modeling
Soil erosion risk was estimated using the RUSLE model, integrates five parameters:
  - Rainfall erosivity (R)
  - Soil erodibility (K)
  - Slope length & steepness (LS)
  - Vegetation cover (C)
  - Conservation practices (P)

Erosion risk levels categorizes:
  - Very Low
  - Low
  - Moderate
  - High
  - Extreme

### WorldPop population data was spatially intersected with hazard zones to estimate affected populations.

Process:
    
    - Overlaying hazard maps with population raster data
    - Extracting population counts within hazard zones
    - Using zonal statistics to calculate the number of inhabitants exposed to each hazard level

### Project Workflow

![Project Workflow]( )

## Tools & Technologies
Software
  - ArcGIS
  - Microsoft Excel

Remote Sensing
  - Landsat imagery 

Spatial Analysis Techniques
  - Supervised Image Classification (Maximum Likelihood)
  - Change Detection
  - Multi-Criteria Decision Analysis (using AHP Weighting and Weighted Overlay)
  - RUSLE soil erosion modeling

## Key Visual Outputs
### Land Cover Change Maps
![Land Cover Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/LULC_1990.jpg)
*Figure 1: land cover map for 1990.*

    
![Land Cover Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/LULC_2002.jpg)
*Figure 2: land cover map for 2002.*


![Land Cover Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/LULC_2015.jpg)
*Figure 3: land cover map for 2015.*


![Land Cover Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/LULC_2025.jpg)
*Figure 4: land cover map for 2025.*


### Flood Hazard Map
![Flood Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/Flood_Vulnerability_Map.jpg)
*Figure 5: Flood hazard map.*


### Soil Erosion Map
![Soil Erosion Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/Soil%20Loss.jpg)
*Figure 6: Soil erosion map.*


### Population Exposure Map
![Population exposure Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/Flood_Affected_Population.jpg)
*Figure 7: Population Exposure Map for flood affected population.*

![Population exposure Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/Erosion_Affected_Population.jpg)
*Figure 8: Population Exposure Map for erosion affected population.*


### *Table 2: Spatial extent of land cover types for the study area (1990 – 2025)*

| Land Use / Cover Class | 1990 (km²) | 2002 (km²) | 2015 (km²) | 2025 (km²) | Change 1990–2002 (km²) | Change 2002–2015 (km²) | Change 2015–2025 (km²) | Total Change 1990–2025 (km²) | % Change |
|------------------------|-----------|-----------|-----------|-----------|------------------------|------------------------|------------------------|-----------------------------|---------|
| Built-Up Area | 12.7053 | 25.4844 | 42.7671 | 59.0283 | 12.7791 | 17.2827 | 16.2612 | 46.323 | 365 |
| Dense Vegetation | 205.8426 | 184.8105 | 173.4759 | 88.4682 | -21.0321 | -11.3346 | -85.0077 | -117.3744 | -57 |
| Sparse Vegetation | 86.6079 | 93.2346 | 90.8073 | 147.4443 | 6.6267 | -2.4273 | 56.637 | 60.8364 | 70 |
| Bare Land / Rock Outcrop | 23.4369 | 25.0632 | 21.5424 | 33.6519 | 1.6263 | -3.5208 | 12.1095 | 10.215 | 44 |
| **Total Area** | **328.5927** | **328.5927** | **328.5927** | **328.5927** |  |  |  |  |  |


### *Table 3: Showing LULC intensity on the gains and losses for the study area (1990-2025)*
| Land Use / Cover Class | Gain (km²) | Loss (km²) | Gain Intensity (%/yr) | Loss Intensity (%/yr) |
|------------------------|-----------|-----------|----------------------|----------------------|
| Built-Up Area | 47.322 | 0.999 | 0.411 | 0.009 |
| Dense Vegetation | 6.449 | 123.823 | 0.056 | 1.077 |
| Sparse Vegetation | 103.375 | 42.539 | 0.898 | 0.369 |
| Bare Land / Rock Outcrop | 26.789 | 16.574 | 0.233 | 0.144 |



## Key Result and Insights
### Results
Land Cover Change - Significant land cover change occurred between 1990 and 2025.

Key trends include:
- Built-up areas increased by 365%
- Dense vegetation declined by 57%
- Sparse vegetation increased significantly
- Bare land also expanded over time
Note: These changes indicate strong urban growth pressure and environmental transformation.

Soil Erosion Risk - The erosion model revealed that:
- ~39% of the area experiences very low erosion
- ~49% experiences low erosion
- ~6% experiences extreme erosion risk

High erosion zones are concentrated in areas with:
- steep slopes
- reduced vegetation cover
- exposed soils

Flood Hazard Distribution - Flood hazard mapping shows that:
- 17% of the region falls within high flood-risk zones
- 82% falls within low flood-risk areas
- Very high hazard zones cover a very small area

Flood hazard is strongly influenced by:
- low elevation
- high flow accumulation
- built-up land surfaces

Population Exposure - The hazard exposure analysis shows:

Flood Exposure
- ~62,000 people live in high flood-risk areas
- Over 528,000 residents are located in low-risk zones but remain vulnerable to severe rainfall events.

Erosion Exposure
- ~47,000 inhabitants live in extreme erosion zones
- ~18,000 people are located in high erosion risk areas
Note: Many high-risk zones coincide with rapidly expanding urban areas and transport corridors.

### Insights
The results highlight several critical relationships:
- Urban expansion is strongly linked to declining vegetation cover
- Increased impervious surfaces contribute to higher flood susceptibility
- Areas experiencing both flood and erosion risks represent compound hazard zones
- Hazard exposure is concentrated around urban settlements and infrastructure corridors
- These findings emphasize the need for sustainable urban planning and improved land management strategies.


## Limitations
While the project provides useful insights, several limitations exist:
- Landsat imagery resolution limits fine-scale analysis
- Rainfall data resolution may not capture local variability
- Assumptions in the RUSLE model may simplify real erosion processes
- Population estimates rely on modeled datasets

## Conclusion
This project demonstrates how GIS and remote sensing techniques can be applied to assess environmental hazards in rapidly land cover changing regions.
By integrating land cover change analysis, flood hazard modeling, and soil erosion estimation, the study provides valuable insights into how land cover influences hydrological 
risks and population exposure.
The workflow can be adapted for urban risk assessment, environmental monitoring, and disaster management planning in other regions.
