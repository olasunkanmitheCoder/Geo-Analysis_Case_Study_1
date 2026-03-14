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
| Data                          | Source                         | Resolution    |
| ----------------------------- | ------------------------------ | ------------- |
| Landsat TM, ETM+, OLI imagery | [USGS](https://earthexplorer.usgs.gov/)                           | 30m           |
| Digital Elevation Model (DEM) | SRTM / USGS                    | 30m           |
| Rainfall Data                 | [TAMSAT](https://data.tamsat.org.uk/)                         | 0.5°          |
| Soil Data                     | [Harmonized World Soil Database](https://iiasa.ac.at/models-tools-data/hwsd) | 30 arc-second |
| Population Density            | [WorldPop](https://hub.worldpop.org/project/categories?id=3)                       | ~1km          |

## Methodology
The workflow involved:

#### Land Cover Classification and Change Detection
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

#### Flood Hazard Modeling and Weighting with Analytical Hierarchy Process (AHP)
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

#### Soil Erosion Modeling
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

#### WorldPop population data was spatially intersected with hazard zones to estimate affected populations.

Process:
    
    - Overlaying hazard maps with population raster data
    - Extracting population counts within hazard zones
    - Using zonal statistics to calculate the number of inhabitants exposed to each hazard level

### Project Workflow

Satellite Imagery → Image Classification → LULC Change Detection
                    ↓
               GIS Layers
                    ↓
      MCDA + AHP Flood Hazard Mapping
                    ↓
           RUSLE Soil Erosion Model
                    ↓
           Population Exposure Analysis

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
    
![Land Cover Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/LULC_2002.jpg)

![Land Cover Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/LULC_2015.jpg)

![Land Cover Map](https://github.com/olasunkanmitheCoder/Geo-Analysis_Case_Study_1/blob/main/LULC_2025.jpg)

### Flood Hazard Map


### Soil Erosion Map


### Population Exposure Map
