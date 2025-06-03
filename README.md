# 🌡️ Temperature Forecasting (2025) Using ERA5 & FBProphet

This repository contains a complete pipeline for building regional temperature forecasting models using **ERA5 hourly reanalysis data** and **Facebook Prophet**.

Although the example here uses Pakistan with 242 hypothetical stations, the pipeline is fully customizable for **any country or region** — just replace the shapefile.

---

## ✅ Project Workflow

### 1. 📍 Generate Hypothetical Stations
- `hypothetical_stations.ipynb`: Creates evenly distributed weather stations using a user-provided boundary shapefile.

### 2. 📦 Subset ERA5 Data by Year
- `merge_clean_data.ipynb`: Subsets large hourly ERA5 NetCDF files (downloaded year-by-year from CDS).
- Saves clipped data per station into yearly folders (e.g., `2015/`, `2016/`…).

### 3. 🔀 Merge Preprocessed Data
- `subset_era5_data.ipynb`: Loads yearly subsets and merges them into a unified CSV dataset suitable for model training.

### 4. 📈 Forecast Temperature Using Prophet
- `fb_prophet_model.ipynb`: Trains a **separate sliding-window forecasting model for each station** using **Facebook Prophet**
- This ensures that localized seasonality, trends, and anomalies are captured independently for each point.
- The notebook example shows training for one station — you can loop through all 242 to scale the forecast.
- Forecasts hourly temperature for **Jan–Feb 2025** and validates against actual ERA5 data.
---

## 🔍 Key Features

- ✅ Regional forecasting using real ERA5 hourly climate data
- ✅ Flexible: works with any shapefile (country, province, etc.)
- ✅ Efficient year-wise subsetting to reduce memory load
- ✅ Time series forecasting using Facebook Prophet
- ✅ Includes RMSE, MAE, R², and visual evaluation plots

---

## 📁 Files in This Repo

- `hypothetical_stations.ipynb` — Generate station points using shapefile
- `subset_era5_data.ipynb` — Subset and save yearly NetCDF data
- `merge_clean_data.ipynb` — Merge yearly subsets into full dataset
- `fb_prophet_model - Temperature.ipynb` — Forecast model + evaluation

---

## 💡 Requirements

Download requirements.txt

Install with:

```bash
pip install -r requirements.txt
```

---

## 🧠 Author

**Shahab Zaib**  
[GitHub](https://github.com/ShahabZaib) | [LinkedIn](https://linkedin.com/in/shahab-zaib-376427247/)

---

## 🔗 License

MIT License — free to use, modify, and distribute.
