# Dmart-sales-and-operational-intelligence-dashboard
This GitHub project features a comprehensive dashboard for DMart's sales and operations. It provides data-driven insights into sales trends, product performance, and regional operations using interactive visuals, enabling informed strategic decision-making and identification of growth opportunities.

Here is a step-by-step guide to building the D-Mart Sales & Operational Intelligence Dashboard using Power BI, addressing all the problem statements and key business questions.
Phase 1: Data Acquisition and Preparation (Power Query Editor)
The first step is to bring the data into Power BI and ensure it is clean and correctly formatted for analysis. 
Get Data:
Open Power BI Desktop.
Click Get Data and select the source type (likely an Excel or CSV file as implied by the dataset overview).
Locate and import your dataset.
Transform Data (Power Query Editor):
Click Transform data to open the Power Query Editor.
Handle Missing Values/Duplicates: Identify columns with missing data and decide whether to remove rows or replace values (e.g., replace missing ages with an average or "Unknown"). Remove duplicate transaction records.
Format Data Types: Ensure columns have the correct data types (e.g., "Order Date" and "Delivery Date" as Date/Time, "Age" as Whole Number, "Pricing" as Decimal Number, "Clicks" as Whole Number).
Create Custom Columns (using Power Query or DAX later):
Order Processing Time: Delivery Date - Order Date to measure efficiency. Format this as a number of days.
Revenue: If not already present, create a column for total price/revenue per transaction.
Apply and Close:
Once cleaning is complete, click Close & Apply to load the data into the Power BI data model. 
Phase 2: Data Modeling and DAX Measures
Establish relationships between tables (if you have multiple, e.g., a separate Products table) and create measures for KPIs. 
Create DAX Measures: In the Data view or Report view, right-click the table and select New Measure.
Total Sales: Total Sales = SUM(Transactions[Revenue])
Total Orders: Total Orders = COUNT(Transactions[OrderID])
Average Order Value (AOV): AOV = AVERAGE(Transactions[Revenue])
Order Cancellation Rate: A more complex measure involving counting 'Cancelled' orders and dividing by total orders. Cancellation Rate = DIVIDE(COUNTROWS(FILTER(Transactions, Transactions[OrderStatus] = "Cancelled")), COUNTROWS(Transactions)) 
Phase 3: Dashboard Visualization and Analysis
Use the visualizations menu to create interactive charts and answer the key business questions. 
General Dashboard Structure
Use KPI Cards at the top to display Total Sales, Total Orders, AOV, and Cancellation Rate.
Add slicers for Order Date (Year, Month), Category, Brand Type, and Region for interactivity. 
Answering Key Business Questions with Visuals
Sales & Revenue Trends
Monthly/Yearly Sales Comparison:
Visual: Line Chart.
Setup: Axis = Order Date (drill down to Year/Month level), Values = Total Sales.
Insight: Helps identify seasonality and overall growth trends.
Contribution of Product Types:
Visual: Donut Chart or Stacked Bar Chart.
Setup: Legend/Axis = Brand Type (Branded, Local, Imported), Values = Total Sales.
Insight: Shows which type drives the most revenue and where to focus inventory/marketing. 
Customer Demographics & Behavior
Customer Distribution (Age and Gender):
Visual: Bar Chart for Age Groups, Donut Chart for Gender.
Setup: Axis (Bar) = Age Group (create a calculated column for bins like 18-25, 26-35, etc.), Values (Bar/Donut) = Count of Customers.
Insight: Highlights the core customer base for targeted marketing.
Website Behavior and Purchase:
Visual: Scatter Plot or Funnel Chart (if you can structure the data).
Setup: X-axis = Time on Website, Y-axis = Clicks, Size/Color = Total Sales (or a measure indicating purchase conversion).
Insight: Determines if more engagement (clicks/time) leads to higher sales, indicating the website's effectiveness.
Product & Pricing Insights
Top Products/Highest Discounts:
Visual: Bar Chart for top products, Table for discount analysis.
Setup: Axis (Bar) = Product Name or Category, Values (Bar) = Total Sales. Table columns: Product Name, Discount %, Total Sales. Use conditional formatting in the table for high discounts.
Insight: Identifies top performers and highlights products with significant markdowns.
Discounted Products and Ratings:
Visual: Scatter Plot or Table with a calculated column for average rating of discounted vs. non-discounted items.
Insight: Helps determine if discounts are effective for product reception/repeat purchases. 
Operational Performance
Shipping Modes Efficiency:
Visual: Bar Chart and KPI card.
Setup: Axis (Bar) = Shipping Mode, Values (Bar) = Average Order Processing Time (Days).
Insight: Pinpoints the fastest and slowest shipping methods, allowing for supply chain optimization.
Order Cancellation Rate/Causes:
Visual: KPI Card for overall rate, Bar Chart to show cancellation breakdown by Product Type or Payment Mode.
Insight: Identifies problematic product types or payment modes associated with cancellations. 
Payment and Order Status
Breakdown of Payment Modes:
Visual: Donut or Pie Chart.
Setup: Legend = Payment Mode (COD, Online, etc.), Values = Total Orders or Total Sales.
Insight: Understands customer preferences and the reliability of each payment method.
Payment Mode & Order Status:
Visual: Clustered Column Chart.
Setup: Axis = Payment Mode, Values = Count of Orders, Legend = Order Status.
Insight: Reveals if any payment mode has a disproportionately high number of 'Pending' or 'Cancelled' orders. 
Phase 4: Presentation and Business Suggestions
Structure your findings for strategic decision-making.
Key Findings: Summarize the main insights (e.g., "Electronics are the highest revenue driver," "Standard shipping is the most used but also slowest," "Customers aged 26-35 make the most purchases").
Graph Insights: Briefly explain what each visual reveals.
Data-backed Business Suggestions:
Focus marketing efforts on the dominant age/gender demographic.
Negotiate better rates or improve processes for the least efficient shipping modes.
Investigate why specific product types have high cancellation rates in certain payment modes and address the root cause. 
Focus marketing efforts on the dominant age/gender demographic.
Negotiate better rates or improve processes for the least efficient shipping modes.
Investigate why specific product types have high cancellation rates in certain payment modes and address the root cause. 
