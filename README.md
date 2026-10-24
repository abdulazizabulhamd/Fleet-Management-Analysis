# Fleet Management Dashboard | Power BI

## 1. Project Overview

This project analyzes fleet operations and financial performance using Microsoft Power BI. The dashboard brings together revenue, delivery volume, transported weight, operating costs, and vehicle performance in an interactive report.

It is designed to help users monitor key performance indicators, compare costs across truck and trailer types, and explore operational trends over time.

### Project Objectives

- Monitor revenue, delivery quantity, and transported weight.
- Analyze fixed and variable operating costs.
- Compare cost per kilometer and cost per ton across vehicle categories.
- Examine relationships between distance traveled, fuel consumption, transported weight, and maintenance costs.
- Review profit and vehicle-level performance.

### Tools and Technologies

- Microsoft Power BI
- Power Query
- DAX
- Data modeling
- Data visualization

## 2. Data Source and Structure

The project data came from three files:

- **Excel Workbook 1:** Dimension tables for `Client`, `Motorista`, and `Veiculo`.
- **Excel Workbook 2:** Cost data for 2018 and 2019, stored in two separate tables.
- **CSV File:** Kilometer-traveled data (`F KM Traveled`).

## 3. Data Preparation and ETL

The ETL process was straightforward. The two cost tables, containing data for 2018 and 2019, were appended in Power Query to create a consolidated cost table.

The report also converts transported weight from kilograms to tons by dividing the total weight in kilograms by 1,000.

## 4. Data Modeling

The data model was planned before implementation, and the dashboard layout was sketched on paper.

A Calendar table was created in DAX using `CALENDARAUTO()` to support time-based analysis and time-intelligence calculations. Year, month, and quarter fields were derived from the date column.

The model brings together the `Client`, `Motorista`, and `Veiculo` dimension tables with the cost and kilometer-traveled data.

## 5. Measures and Key Performance Indicators

The dashboard includes the following measures and KPIs:

- Net Revenue
- Goods Value
- Delivery Quantity
- Weight in Tons
- Fixed Costs
- Variable Costs
- Total Cost
- Cost per Kilometer
- Cost per Ton
- Profit
- Gross Margin Percentage (GM%)
- Number of Trucks Used
- Average Ticket Price (ATP)
- Profit per Kilometer
- Profit per Ton

Net Revenue represents revenue after discounts and other deductions. Goods Value represents the value of the loaded quantities before deductions.

Variable Costs were calculated by adding fuel costs and maintenance costs. Total Cost was calculated as Fixed Costs plus Variable Costs.

The main calculations include:

- **Weight in Tons** = Total Weight in Kilograms ÷ 1,000
- **Cost per Kilometer** = Total Cost ÷ Kilometers Traveled
- **Cost per Ton** = Total Cost ÷ Weight in Tons
- **Profit** = Net Revenue − Total Cost
- **ATP** = Goods Value ÷ Delivery Quantity

## 6. Dashboard Pages

The report contains three pages.

### 6.1 Overview

The Overview page presents four KPI cards:

- Net Revenue
- Goods Value
- Delivery Quantity
- Weight in Tons

It also includes charts showing:

- Net Revenue by the top 15 cities
- Net Revenue over time
- Delivery Quantity over time

### 6.2 Cost Analysis

The Cost Analysis page presents five KPI cards:

- Fixed Costs
- Variable Costs
- Total Cost
- Cost per Kilometer
- Cost per Ton

The charts show:

- The relationship between kilometers traveled and fuel consumption
- The relationship between transported weight in tons and maintenance costs
- Cost per Kilometer by truck type
- Cost per Ton by trailer type

### 6.3 Vehicles Analysis

The Vehicles Analysis page presents KPI cards for:

- Profit
- Delivery Quantity
- Number of Trucks Used
- Weight in Tons
- Kilometers Traveled

It also includes a Gross Margin Percentage (GM%) gauge, a chart comparing Cost and Profit over time, and a matrix organized by Truck Type and Plate.

The matrix includes:

- Goods Value
- Delivery Quantity
- Average Ticket Price (ATP)
- Cost
- Cost per Kilometer
- Cost per Ton
- Profit
- Profit per Kilometer
- Profit per Ton

## 7. Key Insights and Business Opportunities

The dashboard highlights several findings and areas for further review:

- **Cost structure:** Fixed Costs are approximately **$2.60M** out of **$3.77M** in Total Cost, or about **69%**. Variable Costs are approximately **$1.17M**, or about **31%**. This makes the fixed-cost structure an important area to monitor.
- **Operating scale:** The dashboard reports **23 trucks**, approximately **1.18M kilometers traveled**, and **654.17K tons** transported.
- **Cost efficiency:** The displayed overall cost is approximately **$3.20 per kilometer** and **$5.68 per ton**. These measures can be used to compare truck and trailer categories.
- **Geographical performance:** Bloomington is the top city by Net Revenue in the displayed chart, at approximately **$42.4M**.
- **Monthly performance:** The monthly Net Revenue chart shows variation over time, with February standing out as one of the strongest months.

### Potential Business Actions

- Review the main drivers of fixed costs and track how they change over time.
- Compare Cost per Kilometer across truck types and Cost per Ton across trailer types to identify categories for closer operational review.
- Examine monthly revenue and delivery trends together to understand periods with stronger or weaker activity.
- Use the Truck Type and Plate matrix to identify individual vehicles that may need a closer review of cost and profit performance.

## 8. Challenges and Lessons Learned

The ETL work was limited, with the main preparation step being the consolidation of the 2018 and 2019 cost tables.

The project also involved:

- Planning the data model and dashboard layout before building the report.
- Creating a Calendar table to support time-based analysis.
- Combining fuel and maintenance costs into a Variable Costs measure.
- Converting transported weight from kilograms to tons.
- Defining business measures that support cost and vehicle comparisons.

## 9. Conclusion

This project applies Power BI to fleet performance analysis by combining cost, distance, delivery, weight, and vehicle information in one interactive dashboard.

The report provides an overview of fleet operations and enables users to compare costs across truck and trailer types, review performance over time, and explore vehicle-level results. It also demonstrates how a clear data model and well-defined KPIs can turn operational data into useful business information.

## 10. Dashboard Screenshots

Add screenshots of the three report pages to the repository, then update the image paths below to match the filenames.

| Dashboard Page | Screenshot |
|---|---|
| Overview | `images/overview.png` |
| Cost Analysis | `images/cost-analysis.png` |
| Vehicles Analysis | `images/vehicles-analysis.png` |
