# Environmental Analysis of Temperature in California

📦 **Packages**: `readxl`, `ape`, `sp`, `spdep`, `codep`, `spatialEco`, `lattice`, `gstat`, `lctools`, `raster`, `sf`, `rnaturalearth`, `phylin`, `ggplot2`, `tidyverse`, `viridis`

The aim of the project is to study temperature in California and create an interpolation map of temperature there.

## Data Exploration 

- Utilized box plot, bubble plot, and spplot for initial data exploration.

## Autocorrelation

- Employed Moran's I measure, localized Moran's I, and LISA plot for autocorrelation analysis.

## Modelling

### Trend Surface Models

- Fitted trend surface models of first, second, and third degree to the data.

### Inverse Distance Weighting (IDW)

- Applied IDW weighting for interpolation, determining the best parameter 'p' using mean squared error.

### Kriging

- Utilized ordinary kriging with exponential variogram and plotted the prediction map as well as the prediction error map.

# Results

- It's important to study it locally since there are spatial outliers and P=3.951 in IDW. 
- There are clusters (positive autocorrelation), with a strong cluster in low-low quarter (low value of temperature surrounded by low values of temperature). The highest values of temperature are observed in the northwest and east of California, while the lower values are found in the southwest and south of California. 
- We can't rely on ordinary kriging in the southwest and northeast of California since they have the highest prediction error.

## Recommendations

1. Using kriging for interpolation is better since inverse distance weighting assumes no error (mathematical function) and the trend surface model assumes no autocorrelation.
2. Notably, we need more stations in the southwest and northeast of California since they have the highest prediction error [(36.96, 47.61) & (47.61, 58.26)] based on ordinary kriging, with the best predictions in the middle of California.
