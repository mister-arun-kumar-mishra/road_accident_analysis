# road_accident_analysis
![Preview](https://github.com/mister-arun-kumar-mishra/road_accident_analysis/raw/main/preview.png)

## Introduction
This project is aimed at analyzing traffic accident data and identifying trends and insights related to casualties. The project will leverage several key performance indicators (KPIs) to measure the severity and impact of traffic accidents, including the total number of casualties by accident severity, vehicle type, road type, and other factors.

## Business Case:
The business case for this project is to help transportation authorities, law enforcement agencies, and other stakeholders improve traffic safety and reduce the number of casualties caused by accidents. By analyzing accident data and identifying trends and patterns, these stakeholders can implement targeted interventions to improve road safety and reduce the risk of accidents.

## Dashboard Requirements:
* Primary KPI's - Total Casualties and Total Accident values for Current Year and YoY Growth
* Primary KPI's - Total Casualties by Accident Severity for Current Year and YoY Growth
* Secondary KPI's - Total Casualties with respect to Vehicle Type for Current Year
* Monthly Trend showing comparison of Casualties for Current Year and Previous Year
* Casualties by Road Type for Current Year
* Current Year Casualties by Area/Location & Day/Night
* Total Casualties and Total Accident by Location

## Setup
* Install Power BI Desktop from Official [Power BI Download Site](https://powerbi.microsoft.com/en-us/downloads/)
* Download data files from this [link](https://docs.google.com/spreadsheets/d/1Jce1ZECXXy4GFhlaGBv1sPoKLnSR5Oq9/edit?usp=sharing&ouid=112081881269048231033&rtpof=true&sd=true) or from Kaggle
* Clone/download this repository to your local machine
* Open Dashboard report file `Road_Accident_Analysis.pbix` in Power BI Desktop, to access the dashboard's interactivity 

## Formulas Used in Measures

**1. Total Casualties For Current Year (CY) and Year on Year (YOY) Growth**

(a) Current Year To Date Casualties -- CY Casualties Measure
```
CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])
```

(b) Previous Year Casualties -- PY Casualties Measure
```
PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))
```

(c) Year on Year Growth of Casualties - YoY Casualties Measure
```
YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]
```

**2. Total Accidents for Current Year and Year on Year Growth**

(a) Current Year Accidents Count -- CY Accidents Count Measure
```
CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])
```

(b) Previous Year Accidents Count -- PY Accidents Count Measure
```
PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))
```

(c) Year on Year Growth of Accidents - YoY Accidents Measure
```
YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]
```
