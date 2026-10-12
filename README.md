# Sales-Performance-Dashboard

Project Overview
Item	Detail
Tool	Microsoft Excel (PivotTables, PivotCharts, Slicers)
Data	2,000 sales orders, calendar year 2026
Output	One-page interactive sales dashboard
File	Sales_data_cleaning.xlsx
Dataset columns (Sales_data sheet)
Column	Description
Order ID	Unique order number (e.g. ORD-1001)
Date	Order date
Region	Central / East / North / South / West
Sales Channel	Online / Corporate Sales / Retail Store / Marketplace
Customer Type	New / Returning
Product Category	Computers, Monitors, Networking, Storage, Accessories, Office Supplies
Product	Individual product name
Salesperson	Salesperson who closed the order
Quantity	Units sold
Unit Price	Price per unit
Discount	Discount applied (0 – 20%)
Revenue	Quantity x Unit Price x (1 - Discount)

Workbook Structure-Sheet	Purpose
Sales_data	Cleaned source data (A1:L2001)
Pivot table	Six PivotTables and the charts that feed the dashboard
Dashboard	Final presentation sheet: KPI summary, 5 charts, 4 slicers

How I Built It (Step by Step)
Step 1: Import and clean the raw data
Open the raw sales file in Excel and keep the original as a backup copy.
Remove duplicate Order IDs (Data > Remove Duplicates).
Check for blank cells and fix or remove incomplete rows.
Trim extra spaces and standardise text (e.g. consistent Region, Channel and Product names) using TRIM / PROPER or Find & Replace.
Convert the Date column to a proper Date format (yyyy-mm-dd).
Make sure Quantity, Unit Price, Discount and Revenue are numeric.
Confirm Revenue is correct with a check formula: =ROUND(I2*J2*(1-K2),2) and compare it with the Revenue column.
Format the data as an Excel Table (Ctrl + T) so the PivotTables update when data changes.

Edit this section so it matches the exact cleaning steps you applied to your raw file.

Step 2: Create the PivotTables
Go to Insert > PivotTable, choose the Sales_data table and place each pivot on the Pivot table sheet.
#	PivotTable	Rows	Values
1	KPI summary	n/a	Sum of Revenue, Sum of Quantity, Count of Order ID, Average of Revenue
2	Revenue by Month	Date (grouped by Months)	Sum of Revenue
3	Revenue by Region	Region	Sum of Revenue
4	Revenue by Product Category	Product Category	Sum of Revenue (sorted largest to smallest)
5	Revenue by Sales Channel	Sales Channel	Sum of Revenue
6	Top 5 Products	Product	Sum of Revenue, with a Value Filter > Top 10 > Top 5 and sorted descending

Tip: to group dates by month, right-click a date in the PivotTable and choose Group > Months.

Step 3: Create the charts
Select a cell inside each PivotTable and use Insert > PivotChart:
Chart	Type	Source
Revenue By Month	Line chart	PivotTable 2
Revenue By Region	Clustered bar / column	PivotTable 3
Revenue By Product Category	Bar chart	PivotTable 4
Revenue By Sales Channel	Doughnut chart	PivotTable 5
Top 5 Product by Revenue	Bar chart	PivotTable 6
Then clean up each chart: add a clear title, remove unnecessary gridlines and field buttons, and use a consistent colour palette.

Step 4: Build the Dashboard sheet
Insert a new sheet and name it Dashboard.
Turn off gridlines (View > Gridlines) and set a background colour for a clean look.
Add a title banner at the top.
Create KPI cards (text boxes or cells linked to the KPI PivotTable) for Total Revenue, Total Quantity, Total Orders and Average Revenue per Order.
Cut and paste the five charts from the Pivot table sheet onto the Dashboard and arrange them in a grid.

Step 5: Add slicers for interactivity
Select any PivotTable and go to PivotTable Analyze > Insert Slicer.
Add slicers for Region, Sales Channel, Customer Type and Product Category.
Right-click each slicer > Report Connections and tick all PivotTables so one click filters every chart and KPI.
Resize the slicers and place them along the side or top of the dashboard.

Step 6: Final checks and save
Click different slicer combinations and confirm all charts and KPIs update.
Make sure the totals match across pivots (all Grand Totals equal $3,462,605.32).
Hide or move the Pivot table sheet to the end if you only want to show the dashboard.

Key Insights
Total revenue: about $3.46M from 2,000 orders and 7,552 units. Average order value is about $1,731.
Computers drive the business: about $2.06M, roughly 59% of all revenue.
Top product: Gaming Laptop (about $666K). The top 5 products make up around 62% of revenue.
Channels: Online (about $1.11M) and Corporate Sales (about $1.01M) lead. Marketplace is the smallest (about $429K).
Regions: Central is the strongest (about $803K) and West the weakest (about $587K), so performance is fairly balanced.
Seasonality: monthly revenue peaks in June and November and dips in July, with a gap of almost 75% between the best and worst months.
