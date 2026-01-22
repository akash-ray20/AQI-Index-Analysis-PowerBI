# AQI Power BI Dashboard – DAX Documentation

This document contains all DAX measures and calculated columns used in the AQI Power BI dashboard.

## Calendar Table
Month = FORMAT('Calendar Table'[Date], "mmm")
Year = YEAR('Calendar Table'[Date])

## AQI Cat Num (Calculated Column)
AQI Cat Num =
SWITCH(
    TRUE(),
    day_wise_aqi_data[aqi_value] <= 50, 1,
    day_wise_aqi_data[aqi_value] <= 100, 2,
    day_wise_aqi_data[aqi_value] <= 150, 3,
    day_wise_aqi_data[aqi_value] <= 200, 4,
    day_wise_aqi_data[aqi_value] <= 300, 5,
    day_wise_aqi_data[aqi_value] > 300, 6,
    7
)

## AQI Category (Measure)
AQI Category =
VAR AvgAQI = AVERAGE(day_wise_aqi_data[aqi_value])
RETURN
SWITCH(
    TRUE(),
    AvgAQI <= 50, "Good",
    AvgAQI <= 100, "Moderate",
    AvgAQI <= 150, "Poor",
    AvgAQI <= 200, "Unhealthy",
    AvgAQI <= 300, "Very Unhealthy",
    AvgAQI > 300, "Hazardous",
    "NA"
)

## AQI Category (Calculated Column)
AQI category_col =
SWITCH(
    TRUE(),
    day_wise_aqi_data[aqi_value] <= 50, "Good",
    day_wise_aqi_data[aqi_value] <= 100, "Moderate",
    day_wise_aqi_data[aqi_value] <= 150, "Poor",
    day_wise_aqi_data[aqi_value] <= 200, "Unhealthy",
    day_wise_aqi_data[aqi_value] <= 300, "Very Unhealthy",
    day_wise_aqi_data[aqi_value] > 300, "Hazardous",
    "NA"
)

## AQI Level (Measure)
AQI Level =
SWITCH(
    TRUE(),
    day_wise_aqi_data[aqi_value] <= 50, "0-50",
    day_wise_aqi_data[aqi_value] <= 100, "51-100",
    day_wise_aqi_data[aqi_value] <= 150, "101-150",
    day_wise_aqi_data[aqi_value] <= 200, "151-200",
    day_wise_aqi_data[aqi_value] <= 300, "201-300",
    day_wise_aqi_data[aqi_value] > 300, "301-500",
    "NA"
)

## Average AQI (Measure)
avg AQI = AVERAGE(day_wise_aqi_data[aqi_value])

## Count of Rows (Measure)
Count of Rows = COUNTROWS(day_wise_aqi_data)

## KPI Title (Measure)
KPI Title = SELECTEDVALUE(day_wise_aqi_data[state])

## Primary Pollutant (Measure)
Primary Pollutant =
VAR PollutantTable =
    SUMMARIZE(
        day_wise_aqi_data,
        day_wise_aqi_data[prominent_pollutants],
        "PollutantCnt", COUNTROWS(day_wise_aqi_data)
    )
VAR MaxCnt =
    MAXX(PollutantTable, [PollutantCnt])
RETURN
    CONCATENATEX(
        FILTER(PollutantTable, [PollutantCnt] = MaxCnt),
        day_wise_aqi_data[prominent_pollutants],
        ","
    )



