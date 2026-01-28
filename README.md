# CASA Liquidity Data Validation Dashboards

Interactive dashboards for CASA (Current Account + Savings Account) liquidity risk modeling and data validation.

## 🔗 Live Demo

**View Dashboards**: [Coming Soon - After Render Deployment]

## 📊 Overview

This project provides comprehensive data validation dashboards for 10-year CASA liquidity data (2017-2026) with 3,651 daily records.

### What's Included:

- **Executive Summary Dashboard** - Overall validation results and data quality score
- **7 Detailed Validation Check Dashboards**:
  1. Data Quality (Missing data, Outliers, Duplicates)
  2. Detrending Analysis (Trend detection and removal)
  3. Seasonality Tests (Month-end effects, ACF/PACF)
  4. Stationarity Tests (ADF, KPSS, Rolling statistics)
  5. Normality Tests (Distribution analysis, Q-Q plots)
  6. Volatility Analysis (ARCH-LM, Heteroskedasticity)
  7. **NEW:** Macro Correlation Analysis (Correlation with macro indicators)

## 🎯 Key Findings

### Current Account (CA):
- **Trend**: -50.9% decline over 10 years
- **Outliers**: 161 detected (high volatility)
- **Stationarity**: STATIONARY (ADF p=0.011)
- **Normality**: NON-NORMAL (extreme fat tails, kurtosis=189.75)
- **Data Quality**: 36 missing values (0.99%)

### Savings Account (SA):
- **Trend**: +85.3% growth over 10 years
- **Outliers**: 53 detected (moderate stability)
- **Stationarity**: NON-STATIONARY (ADF p=0.562)
- **Normality**: NON-NORMAL (heavy tails, kurtosis=109.64)
- **Data Quality**: 36 missing values (0.99%)

### Overall Data Quality Score: **73/100**

## 🚀 How to Use

### Online (Recommended):
1. Visit the live dashboard URL
2. Start with the main page (Executive Summary)
3. Click links to navigate to detailed check dashboards
4. All visualizations are interactive (zoom, pan, hover)

### Local:
1. Clone this repository
2. Open `index.html` in your web browser
3. No installation required - all dashboards are self-contained

```bash
git clone https://github.com/Akshit7103/CASA-LIQUIDITY-DATA-VALIDATION.git
cd CASA-LIQUIDITY-DATA-VALIDATION
# Open index.html in browser
```

## 📁 Project Structure

```
deployment_v2/
├── index.html                     # Executive Summary (start here)
├── dashboards/
│   ├── Check1_DataQuality_Dashboard.html
│   ├── Check2_Detrending_Dashboard.html
│   ├── Check3_Seasonality_Dashboard.html
│   ├── Check4_Stationarity_Dashboard.html
│   ├── Check5_Normality_Dashboard.html
│   ├── Check6_Volatility_Dashboard.html
│   └── Check8_MacroCorrelation_Dashboard.html
├── render.yaml                    # Render deployment config
├── .gitignore
└── README.md
```

## 💡 Features

- **Interactive Visualizations**: Powered by Plotly
  - Zoom into specific time periods
  - Hover for exact values
  - Pan across data
  - Download plots as PNG

- **Self-Contained**: No external dependencies
  - All data embedded in HTML files
  - Works offline
  - No database or API needed

- **Comprehensive Analysis**:
  - Multi-panel layouts
  - CA vs SA side-by-side comparisons
  - Statistical test results included
  - Color-coded status indicators

## 📈 Modeling Recommendations

Based on validation results:

| Aspect | Recommendation | Reason |
|--------|---------------|---------|
| **Missing Data** | Linear Interpolation | Best RMSE, preserves temporal patterns |
| **Outliers** | IQR Capping (SA), Careful Review (CA) | SA: 12.74% improvement; CA: High natural volatility |
| **Stationarity** | First Differencing (SA only) | SA is non-stationary, needs transformation |
| **Volatility** | GARCH/EGARCH Models | Strong heteroskedasticity detected |
| **Distribution** | Non-parametric Methods | Data is non-normal with extreme fat tails |
| **Macro Correlation** | Include in models | Significant correlations detected |

## 🛠️ Technical Details

- **Data Period**: 2017-01-01 to 2026-12-31 (10 years, 3,651 days)
- **Visualization**: Plotly (interactive JavaScript charts)
- **File Format**: Static HTML (no server required)
- **Total Size**: ~3.7 MB (embedded plot data)

## 📞 Contact

**Project**: CASA Behavioral Liquidity Risk Modeling & Outflow Estimation Framework

**Author**: Akshit Mahajan
**Role**: Consultant 1 - Risk and Compliance
**Email**: akshit.mahajan@protivitiglobal.in
**Phone**: +91 7003006208

## 📄 License

Internal use - Protiviti Global

## 🙏 Acknowledgments

- Risk Management Team
- Data Validation Framework
- CASA Liquidity Modeling Project

---

**Last Updated**: January 28, 2026
**Version**: 2.0
**Status**: Production Ready
