# sales-report-dashboard

## Power BI Dashboard Design for Sales, Profit, and Quantity Tracking

## Objective:
To create a dynamic Power BI dashboard that allows users to track and analyze key business metrics—Sales, Profit, and Quantity—across four regions: Central, East, South, and West. The dashboard should provide year-based filtering and allow users to switch between different metrics. Additionally, it should compare the selected year's Sales with the Previous Year's (PY) Sales.

## Dashboard Features:

## Dynamic Metric Selection
Users can toggle between Sales, Profit, and Quantity using a selection button or slicer.
## Regional Performance Breakdown
Visual representation of data segmented by Central, East, South, and West regions.
## Yearly Filter
A dropdown or slicer to filter data by year.
## Comparison with Previous Year (PY) Sales
A visual comparison of the selected year's Sales against the previous year's Sales.
Percentage growth/decline indicator.
## Key Visuals & Elements:
Bar Chart: Displays the selected metric (Sales, Profit, or Quantity) by region.
Line Chart: Shows trends over the years for Sales, Profit, or Quantity.
KPI Cards: Displays Total Sales, Profit, and Quantity for the selected year.
Comparison Chart: Side-by-side bar chart for Sales vs. PY Sales.
## Interactivity & User Controls:
Dropdowns or buttons for metric selection.
A year slicer to select the desired time frame.
Hover tooltips to show detailed information for each data point.
## Implementation Steps:
Data Preparation
Load sales data, ensuring it includes Year, Region, Sales, Profit, and Quantity.
Create a calculated column for Previous Year (PY) Sales.

## Measure Creation (DAX):
Selected Metric = SWITCH(SELECTEDVALUE(MetricSelection[Metric]), "Sales", SUM(Sales[Amount]), "Profit", SUM(Sales[Profit]), "Quantity", SUM(Sales[Quantity]))
PY Sales = CALCULATE(SUM(Sales[Amount]), SAMEPERIODLASTYEAR(Sales[Date]))
Sales Growth % = DIVIDE([Sales] - [PY Sales], [PY Sales], 0)
## Dashboard Layout & Formatting
Arrange visuals for easy comparison and analysis.
Use color coding to highlight positive/negative growth.
Ensure a responsive design for different screen sizes.
