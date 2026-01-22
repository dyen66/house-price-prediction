# **House Price Prediction & Economic Analysis**

An analytical project focused on modeling U.S. house price trends by integrating real estate market data with key macroeconomic indicators. This pipeline processes historical housing data alongside mortgage rates, vacancy levels, and inflation metrics to provide an adjusted view of market value over time.

## **🚀 Overview**

Predicting house prices requires understanding the broader economic context. This project automates the extraction and cleaning of Federal Reserve economic data and Zillow real estate metrics. By adjusting historical prices for inflation (CPI), the model provides a "real-dollar" perspective on housing market growth.

### **Key Features**

* **Multi-Source Data Ingestion**: Combines FRED economic indicators with Zillow's weekly and monthly market indices.  
* **Time-Series Alignment**: Synchronizes disparate data frequencies (weekly vs. monthly) using advanced date-time indexing and forward-filling techniques.  
* **Inflation Adjustment**: Implements a Consumer Price Index (CPI) normalization to calculate `adjusted_price`, allowing for accurate historical comparisons.  
* **Visual Trend Analysis**: Generates comprehensive line plots to visualize raw prices against macroeconomic shifts.

## **🛠️ Tech Stack**

* **Language**: Python  
* **Data Manipulation**: `pandas`, `NumPy`  
* **Time-Series Handling**: `datetime`  
* **Visualization**: `matplotlib`

## **📋 Data Sources**

The project utilizes the following datasets:

1. **Federal Reserve (FRED)**:  
   * `MORTGAGE30US`: 30-Year Fixed Rate Mortgage Average.  
   * `RRVRUSQ156N`: Rental Vacancy Rate.  
   * `CPIAUCSL`: Consumer Price Index (Inflation metric).  
2. **Zillow Research**:  
   * `Metro_median_sale_price`: Weekly median sale prices for SFR/Condo.  
   * `Metro_zhvi`: Monthly Zillow Home Value Index (ZHVI).

## **⚙️ Implementation Workflow**

1. **Ingestion**: Load FRED files and Zillow CSVs using custom parsing for dates and indices.  
2. **Preprocessing**: Apply forward filling (`ffill()`) to handle missing values and align weekly mortgage data with monthly CPI/Vacancy data.  
3. **Transformation**:  
   * Merge datasets on monthly periods.  
   * Shift Federal Reserve data indices to account for reporting lags.  
4. **Feature Engineering**: Calculate inflation-adjusted prices to normalize data across different decades.  
5. **Analytics**: Visualize the relationship between interest rates, vacancy, and market value.