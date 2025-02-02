
# Exploratory Data Analysis (EDA) on CalCOFI Oceanographic Dataset with R Programming

## 📌 Project Overview
This project analyzes the **CalCOFI (California Cooperative Oceanic Fisheries Investigations) dataset**, one of the world's longest-running and most comprehensive oceanographic datasets. The dataset contains measurements of **temperature, salinity, dissolved oxygen, chlorophyll-a, and nutrients** from seawater samples collected since **1949** and contains 864,863 rows of data.

## 📂 Dataset Information
- **Source:** [CalCOFI Bottle Database](https://calcofi.org/data/oceanographic-data/bottle-database/)
- **Number of Variables:** 74
- **Key Variables Analyzed:**
  - **T_degC**: Water temperature (°C)
  - **Salnty**: Salinity (Practical Salinity Scale 1978)
  - **O2ml_L**: Oxygen concentration (ml/L)
  - **STheta**: Potential density (Kg/m³)
  - **Depthm**: Measurement depth (m)

## 🛠️ Data Preprocessing
1. **Data Cleaning**:
   - Handled **missing values** (e.g., `NA`s were omitted due to large dataset size).
   - Removed **duplicates** to improve accuracy.
   - Filtered outliers for key variables.

2. **One-Variable Analysis**:
   - **Histograms & Boxplots** were used to understand distributions.
   - Example finding: **Most temperature values were around 10°C**.

3. **Two-Variable Analysis**:
   - **Scatterplots** revealed relationships between variables.
   - **Salinity vs. Temperature**: **Inverse correlation** (as temperature increases, salinity decreases).
   - **Depth vs. Temperature**: **Negative correlation** (as depth increases, temperature decreases).

## 📊 Statistical & Machine Learning Models
### 📌 Correlation Analysis
- **Temperature & Salinity:** \( r = -0.5049 \) (moderate negative correlation)
- **Temperature & Oxygen Concentration:** \( r = 0.7949 \) (strong positive correlation)
- **Temperature & Potential Density:** \( r = -0.9640 \) (very strong negative correlation)
- **Temperature & Depth:** \( r = -0.6670 \) (moderate negative correlation)

### 📌 Regression Models
1. **Simple Linear Regression**
   - **Temperature as the dependent variable**
   - Independent variables tested: **Depth, Salinity, Oxygen, Potential Density**
   - **Example result**: Temperature decreases **0.009°C per meter of depth**.

2. **Multiple Linear Regression**
   - **Best Model (`catmodel2`)** included **Salinity, Oxygen, Potential Density, and Depth**.
   - **R² = 99.38%** (very high explanatory power).

3. **Stepwise Regression**
   - **Backward, Forward, and Both-direction methods** confirmed that all variables in the best model were statistically significant.

## 📌 Key Insights
- **Temperature & Salinity are inversely related**, meaning **higher temperatures lead to lower salinity**.
- **Deeper ocean layers have lower temperatures**, with near **0°C at 4000m depth**.
- **Potential density strongly influences temperature**, proving critical for oceanographic models.
- **Oxygen concentration and temperature are positively correlated**, meaning warmer water contains more dissolved oxygen.
