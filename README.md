# cosc3043-deloitte-group2
RMIT COSC3043 Industry Project – Deloitte Waste Trends Analysis (Group 2)

## Notebooks

1. `data_cleaning.ipynb` – Cleans raw source files, cleaned data stored in `Dataset/Cleaned/`
2. `data_preprocessing_model.ipynb` – Feature engineering and preprocessing for ML; stored preprocessed data in `Dataset/ML/`
3. `data_preprocessing_dashboard.ipynb` – Prepares dashboard-ready dataset
4. `forecasting.ipynb` – Baseline Model Development
5. `forecast_optimzed` - Final Optimized Model Development

## Data Folders

```
Dataset/
  Raw/                        Source files (do not modify)
  Cleaned/
    cleaned_vlgas.csv         Victorian Local Government Area waste data (VLGAS)
    cleaned_vwp.csv           Victorian Waste Production by material/stream (VWPPM)
    cleaned_melbourne.csv     City of Melbourne monthly waste collection data
  ML/
    annual_by_lga.csv         Council level aggregated data for Forecasting
    annual_waste.csv          Statewide aggregated data for forecasting
  Semantic Model/             Processed dataset for Power BI semantic model
    dim_council_year.csv
    dim_council.csv
    dim_year.csv
    dim_material.csv
    dim_source_sector.csv
    fact_waste_lga.csv
    fact_waste_flow.csv
    fact_forecast_annual_waste.csv
    fact_forecast_annual_council_waste.csv
  LGA_POLYGON/                 External source for LGA/Councils geo coordinates data
```


## Derived Indicators

### 1. Municipal Waste Generation
Derived as the sum of:
- Garbage
- Recycling
- FOGO
- GO
- Hard Waste
- Glass

**Formula:** `Municipal Waste Generation = Garbage + Recycling + FOGO + GO + Hard Waste + Glass`


### 2. Diversion Rate (including scenario modelling)

**Formula:** `Diversion Rate = (Total Waste Generation − Disposal) / Total Waste Generation`


### 3. Waste Per Capita

#### Total Waste Per Capita

**Formula:** `Total Waste Per Capita = Total Waste Generation / Population`

#### Municipal Waste Per Capita

**Formula:** `Municipal Waste Per Capita = Municipal Waste Generation / Population`


### 4. Organics Materials Diversion Rate

**Formula:** `Organics Diversion Rate = (Total Organics − Organics Disposal) / Total Organics`


### 5. Average Kerbside Diversion Rate

**Formula:** `Average Kerbside Diversion Rate = Sum of all Council Kerbside Diversion Rates / Number of Councils`
