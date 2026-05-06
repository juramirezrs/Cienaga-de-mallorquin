# Water Quality Analysis and Prediction — Ciénaga de Mallorquín

## Language Note
This project is developed and written in Spanish.  
This README is provided in English for accessibility.

---

## Project Overview

How can we detect when an ecosystem is starting to lose its ability to sustain life?

This project analyzes the evolution of water quality in the Ciénaga de Mallorquín (Barranquilla, Colombia) between 2020 and 2024 using real satellite and meteorological data. It also builds predictive models to anticipate future changes.

The goal is to identify early warning signals of environmental degradation and predict future risks.

---

## Objectives

- Analyze water quality indicators (2020–2024)  
- Detect structural change points  
- Forecast future behavior (12 months)  
- Evaluate extreme climate scenarios  

---

## Research Question

**Is it possible to detect critical change points in water quality time series and predict degradation before irreversible damage occurs?**

---

## Data Sources

### **Satellite Data (Sentinel-2)**
- Bands:
  - **B3** (Green)
  - **B4** (Red)
  - **B5** (Red Edge)
  - **B8** (NIR)

### **Meteorological Data (NASA POWER)**
- Temperature (**T2M**)  
- Humidity (**RH2M**)  
- Wind speed (**WS2M**)  
- Precipitation (**PRECTOT**)  
- Solar radiation  

---

## Methodology

### **1. ROI Definition**
Manual polygon created in Google Earth Engine.

### **2. Data Processing**
- Cleaning inconsistent dates  
- Monthly aggregation  
- Merging datasets  
- Interpolation of missing values  

### **3. Exploratory Data Analysis (EDA)**
- Time series  
- Boxplots  
- Histograms  
- Correlation matrix  

### **4. Change Point Detection**
Using `ruptures` to identify structural breaks.

### **5. STL Decomposition**
- Trend  
- Seasonality  
- Residuals  

### **6. WQI-Proxy Construction**
Composite index (0–100) based on weighted indicators.

### **7. Time Series Modeling**
- **ARIMA optimization (AIC)**
- In-sample fitting  
- Rolling forecast (12 months)  

### **8. Extreme Scenario Simulation**
Drought stress test on ecosystem variables.

---

## Key Indicators

- **NDWI** → Water presence  
- **NDCI (Chlorophyll)** → Biological productivity  
- **Turbidity** → Suspended particles  
- **SPM** → Suspended solids  
- **Transparency** → Water clarity  

---

## GeoGebra Formulas

### **NDWI**

(B3 - B8) / (B3 + B8)


### **NDCI**

(B5 - B4) / (B5 + B4)


### **Turbidity (simple proxy)**

B4 / B3


### **Normalized Turbidity**

(B4 - B3) / (B4 + B3)


---

## Main Findings

- **NDWI decreases** → loss of water stability  
- **Turbidity increases** → sediment accumulation  
- **Chlorophyll increases** → potential eutrophication  
- **Transparency decreases** → declining water quality  

### **Critical Insight**
Structural breaks appear around **2021–2022**, linked to:
- infrastructure development  
- human activity  
- climate variability  

---

## Forecast Results

- Turbidity continues increasing  
- NDWI continues decreasing  
- Chlorophyll remains volatile  
- Overall degradation trend persists  

---

## Extreme Scenario (Drought)

- NDWI ↓  
- Turbidity ↑  
- Transparency ↓  
- WQI → **Deficient level**  

### **Interpretation**
The ecosystem shows **low resilience** to extreme climate events.

---

## Limitations

- Only 5 years of data  
- Limited spatial resolution  
- ARIMA is univariate  
- Missing meteorological values  

---

## Future Work

- Multivariate models (**VAR, Prophet, LSTM**)  
- More environmental variables  
- Higher resolution data  
- Real-time monitoring  

---

## Conclusion

The ecosystem is not yet critical, but it is clearly degrading.

**Key insight:**  
Changes in environmental quality are not random.  
They can be **measured, detected, and predicted**.
