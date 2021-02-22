# Validating ASTER Thermal Infrared Imaging for use in Snow Models
#### Calista Moore

## Summary
I will use zonal statistics to analyze how well ASTER TIR data emulates coincident finer resolution airborne TIR for use in snow models. I would like to use NDVI to understand if vegetation impacts the results and identify a scaling function if ASTER does not capture surface temperature well enough for snow models.

## Background
Snowmelt plays an essential role in the hydrologic cycle, contributing up to 75% of water supply in parts of the western United States and having the potential to cause major floods across the globe (Dettinger, M. 2005). As a result, estimating the timing and magnitude of snowmelt is an integral water resources challenge; snow surface temperature observations are key to this issue. It is well established that snow melts at 0°C, so frequent snow temperature measurements supply crucial information for evaluating snowmelt. However, few ground observations of snow surface temperature are available, and those that are only represent a small area. 
By measuring infrared radiation, satellite thermal imaging can remotely determine surface temperature of snow over large areas and time scales where ground observations are sparse or nonexistent. However, this imaging can be limited by its coarse spatial resolution, which results in a blurring of temperatures across study regions. This project investigates how satellite thermal infrared imaging represents snow surface temperature for an improved understanding of snowmelt timing and magnitude over larger spatial areas and timescales. 

## Questions
1. Does the 90 meter resolution ASTER thermal infrared imagery accurately capture the  mean snow surface temperature over the upper Tuolumne area in Yosemite, California? 
2. If ASTER does not accurately represent the mean snow surface temperature, is there an explanation for errors (topography, vegetation, etc.) and a function to correct ASTER?

## Datasets
* [ASTER](https://asterweb.jpl.nasa.gov/) 90-meter TIR
* Airborne 5-meter TIR collected by [UW Applied Physics Lab](https://www.apl.washington.edu/)
* Ground observations collected by [UW Mountain Hydrology Research Group](https://www.apl.washington.edu/)

## Tools/Packages
* [pandas](https://pandas.pydata.org/)
* [numpy](https://numpy.org/)
* [geopandas](https://geopandas.org/)
* [rasterio](https://rasterio.readthedocs.io/en/latest/)
* [matplotlib](https://matplotlib.org/stable/index.html)
* [rioxarray](https://corteva.github.io/rioxarray/stable/)

## Methodology
1. Pick airborne mosaic which aligns with ASTER observations
2. Validate airborne mosaic with two available ground observations
3. Resample rasters as necessary
4. Clip ASTER raster to airborne mosaic
5. Apply zonal statistics over coincident study areas for mean and median temperature
6. Calculate NDVI across study area
7. Identify scaling function for ASTER if necessary

## Expected Outcomes
* Maps with how well ASTER captures surface temperature
* Scaling function using NDVI to improve ASTER accuracy

## References
Dettinger, M. (2005). Changes in streamflow timing in the western United States in recent decades. USGS Numbered Series. [doi:10.3133/fs20053018](doi:10.3133/fs20053018)
Pestana, S., Chickadel, C. C., Harpold, A., Kostadinov, T. S., Pai, H., Tyler, S., et al. (2019). Bias correction of airborne thermal infrared observations over forests using melting snow. Water Resources Research, 55. [https://doi.org/10.1029/2019WR025699](https://doi.org/10.1029/2019WR025699)