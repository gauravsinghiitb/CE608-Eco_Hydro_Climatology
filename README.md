# Climate Variable Trend Analysis of Maldives (1990–2025)

This project analyzes long-term spatial and seasonal trends in key climate variables — temperature (2m), precipitation, specific humidity, and relative humidity — using GRIB-format reanalysis data from 1990 to 2025.

## 📊 Objective

To extract, process, and visualize the trends of climatic variables across time and space, and understand how they vary seasonally and geographically.

---

## 🗂️ Data Source

- **Dataset**: ERA5 Reanalysis Data
- **Provider for Temperature and Precipitation Data**: [Copernicus Climate Data Store (CDS)](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels?tab=download)
- - **Provider for Humidity Data**: [Copernicus Climate Data Store (CDS)](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-pressure-levels?tab=download)
- **Format**: GRIB
- **Resolution**: ~0.25° x 0.25°
- **Variables Used**:
  - `t2m` (2 meter temperature)
  - `tp` (total precipitation)
  - `r` (relative humidity)
  - `q` (specific humidity)

---

## ⚙️ Tools & Libraries

- Python
- xarray
- numpy
- pandas
- matplotlib
- scipy (linregress)
- cfgrib (for reading GRIB files via xarray)

---

## 📌 Methodology

### 1. **Data Preprocessing**
- Loaded GRIB data using `xarray` and `cfgrib`.
- Extracted variables and converted time to datetime format.
- Derived `years` and `seasons` from time.

### 2. **Trend Computation**
- For each grid cell:
  - Extracted time series of the variable.
  - Performed linear regression using `scipy.stats.linregress`.
  - Considered trends statistically significant only if **p-value < 0.05**.
 
---


### 3  **Methodology**
- **Data Preprocessing:** Extraction of relevant variables from GRIB files and conversion to time series.
- **Temporal Analysis:**
  - Monthly and yearly aggregation
  - Trend detection using linear regression and Mann-Kendall test
  - Seasonal decomposition
- **Spatial Analysis:**
  - Latitudinal trend extraction
  - Trend slope calculation and plotting
- **Visualization:** All trends were visualized using time series plots, bar graphs, and geospatial contour maps.

---

## 📈 Results

- **Temperature**: Warming trends observed in most regions, especially during summer months.
- **Precipitation**: Mixed trends; some regions showing significant drying or wetting patterns.
- **Humidity**: Variations in specific and relative humidity trends depend on both geography and season.


