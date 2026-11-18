# Week 5 – Morocco Electricity Consumption and Environmental Factors Analysis
**AnalystLab Africa – Track 1: Data Analytics**
Author: Your Full Name

## Project summary
Exploratory analysis and interactive visualisation of 52,416 electricity-consumption readings (10-minute intervals, 1 Jan – 30 Dec 2017) from three zones in Morocco, together with temperature, humidity and wind speed. The project identifies consumption patterns, compares the zones, tests relationships with environmental factors and gives business recommendations.

## Files in this folder
| File | What it is |
|---|---|
| `week5_power_consumption_analysis.ipynb` | The completed Jupyter notebook (all tasks) |
| `powerconsumption.csv` | Original dataset (supplied) |
| `powerconsumption_datadictionary.csv` | Data dictionary (supplied) |
| `cleaned_power_consumption.csv` | Cleaned dataset with Year, Month, Day, Hour, DayOfWeek, Date columns |
| `charts/` | Chart images (PNG) used in the report |
| `Week5_Analytical_Report.pdf` | Short analytical report |
| `README.md` | This file |

## Tools and libraries
Python 3, Jupyter Notebook (Google Colab), Pandas, NumPy, SciPy (Spearman correlation), Matplotlib, Seaborn, Plotly.
Install locally if needed: `pip install pandas numpy scipy matplotlib seaborn plotly jupyter`

## How to reproduce the analysis
1. Open `week5_power_consumption_analysis.ipynb` in Google Colab (or Jupyter Notebook).
2. Put `powerconsumption.csv` in the same place as the notebook. In Colab, run the upload cell and choose the file.
3. Run all cells from top to bottom (Runtime → Run all).
4. The notebook cleans the data, saves `cleaned_power_consumption.csv`, runs the analysis and draws the charts.

## Data preparation steps
- Datetime converted with format `%m/%d/%Y %H:%M`.
- Checked missing values, duplicate rows, duplicate timestamps and 10-minute spacing (none missing, none duplicated, all gaps 10 minutes; 31 December is absent).
- Outliers investigated with the IQR rule; Zone 3 high values fall in July–August and were kept as genuine peaks.
- Added Year, Month, Day, Hour, DayOfWeek and Date columns.

## Assumptions and notes
- The unit is listed as kWh but the values behave like a power level (kW) per reading, so readings were averaged and not summed into total energy.
- GeneralDiffuseFlows and DiffuseFlows behave like solar radiation, not emissions; they were not used for conclusions.
- Spearman correlation was used because wind speed is bimodal and relationships are not straight lines.
- Correlation is not causation. The data covers a single year.
