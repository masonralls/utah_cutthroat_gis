## Road Disturbance Across the Weber River Basin

This project investigates how landscape characteristics influence human disturbance across a river network in the Weber River Basin, Utah. Using GIS-based feature engineering and statistical analysis, I quantified road density near stream reaches and explored how it relates to elevation, slope, and watershed structure.

The goal is to better understand how infrastructure development interacts with topography and hydrology—an important consideration for aquatic habitat conservation

## Study Area

![alt text](<../figures/Study Area Weber Basin.png>)

The Weber River Basin is a mountainous watershed in northern Utah characterized by steep headwaters and developed valley corridors.

## Data Sources
- USGS 3DEP 1/3 arc-second DEM (10m resolution)
- Stream Network: Utah AGRC Hydrography Dataset
- Roads: Utah Transportation Dataset
- Elevation: Digital Elevation Model (DEM)
- Derived Variables: Generated in QGIS using spatial analysis tools

## Methodology
GIS Processing (QGIS)

- Generated 250 m buffers around each stream reach
- Calculated total road length within each buffer
- Derived road density (km/km²)
- Computed zonal statistics:
    - Mean elevation
    - Mean slope
    - Drainage area

Data Preparation (Python)

- Exported processed dataset as GeoPackage
- Log-transformed skewed variables:
    - Drainage area
    - Road density

- Handled zero-road reaches appropriately

## Exploratory Analysis
Variable Distributions

![alt text](../figures/distributions.png)

Correlation Between Predictors

![alt text](../figures/corr_matrx.png)

- Weak correlations between predictors indicate low multicollinearity
- Road density shows a negative relationship with elevation and slope

Landscape Drivers of Disturbance

![alt text](<../figures/Elevation Map.png>)

- Road density decreases with elevation
- Higher disturbance is concentrated in accessible, lower-elevation terrain
- Headwater streams exhibit lower levels of infrastructure development

Spatial Distribution of Road Disturbance

![alt text](<../figures/rd dens map.png>)

- Road infrastructure is concentrated along major valley corridors
- High-elevation headwaters remain relatively undisturbed
- Spatial patterns align with terrain accessibility and watershed structure

Key Insights

- Road density is strongly influenced by elevation and slope
- Flatter, lower-elevation regions experience higher human disturbance
- High-elevation headwaters represent relatively intact habitat zones
- Drainage area is largely independent of disturbance at this scale

## Modeling (In Progress)

A predictive modeling component will be added using a Random Forest approach to quantify the relative importance of landscape variables in explaining road disturbance patterns.

Planned steps:

- Train/test split
- Random Forest regression
- Feature importance analysis
- Model evaluation (R², RMSE)

## Tools & Technologies

- QGIS — spatial analysis and feature engineering
- Python — GeoPandas, Pandas, NumPy, Matplotlib, Seaborn
- Git/GitHub — version control and documentation

## Future Work

- Incorporate ecological response variables (e.g., trout presence)
- Extend model to habitat suitability prediction
- Integrate land cover and climate datasets
- Analyze temporal changes in disturbance

## Author

Mason Ralls
Applied Mathematics | GIS & Environmental Data Analytics

This project reflects my interest in applying quantitative and geospatial methods to conservation and natural resource management.