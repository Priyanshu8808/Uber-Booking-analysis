# Uber Booking Analysis Dashboard

[![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-blue)](https://powerbi.microsoft.com/) 
[![SQL](https://img.shields.io/badge/SQL-Database-orange)](https://www.microsoft.com/en-us/sql-server/) 
[![Excel](https://img.shields.io/badge/Excel-Data%20Prep-green)](https://www.microsoft.com/en-us/microsoft-365/excel)

---

## Project Overview
This Power BI dashboard provides a comprehensive analysis of **Uber bookings**, handling **100,000+ rows of data** efficiently. It includes dynamic visualizations, interactive insights, and advanced DAX measures to understand booking patterns, cancellations, and performance metrics.  

The workflow combines **SQL, Excel, and Power BI** to process, analyze, and visualize large datasets effectively.

---

## Dataset
- Sourced from **[Kaggle](https://www.kaggle.com/)**  
- Contains **100,000+ rows** of Uber booking data  
- Columns include:  
  - `Booking_ID`: Unique identifier for each booking  
  - `Customer_ID`: Unique ID for the customer  
  - `Driver_ID`: Unique ID for the driver  
  - `City`: City where the ride was booked  
  - `Cab_Type`: Type of cab (e.g., UberX, UberGo, SUV)  
  - `Booking_Date`: Date and time of booking  
  - `Booking_Status`: Status of booking (`Completed`, `Canceled by Customer`, `Canceled by Driver`)  
  - `Fare`: Fare amount for the ride  
  - `Distance`: Distance of the ride  
  - `Pickup_Location`: Starting location of the ride  
  - `Drop_Location`: Destination of the ride  
  - `Payment_Method`: Method of payment (e.g., Cash, Card, Wallet)  
  - `Driver_Rating`: Rating given by customer to driver  
  - `Customer_Rating`: Rating given by driver to customer  

---

## Tools & Technologies
- **SQL:** Data cleaning, filtering, aggregation, and generating insights before importing into Power BI.  
- **Excel:** Pre-processing, pivot tables, exploratory data analysis, and validating data.  
- **Power BI:** Interactive dashboards with dynamic visualizations and KPIs.  
- **DAX:** Advanced metrics including cancellation rate, revenue, and performance KPIs.  

---

## Key Features
- **Dynamic Visualizations:** Interactive charts and slicers to filter data by date, city, cab type, or booking status.  
- **Booking Analysis:** Trends in total bookings, completed rides, and cancellations.  
- **Cancellation Rate Analysis:**  
  - **Cancellation Count** and **Cancellation Percentage** using DAX.  
  - Compare cancellation trends over time and across regions.  
- **Revenue & Performance Metrics:** Analyze total revenue, average fare, and trip distance.  
- **Time-based Insights:** Hourly, daily, and monthly booking patterns.  
- **User-friendly Dashboard:** KPIs, trend charts, and slicers for quick actionable insights.  

---

## DAX Measures
```DAX
-- Total Bookings
TotalBooking = COUNTROWS(july)

-- Cancelled Bookings
CancelledBooking = 
CALCULATE(
    COUNTROWS(july), 
    July[Booking_Status] IN {"Canceled by Driver", "Canceled by Customer"}
)

-- Cancellation Percentage
CanceledPercent = DIVIDE([CancelledBooking], [TotalBooking], 0) * 100


## Workflow

Data Extraction & Cleaning (SQL)
Remove duplicates, filter invalid rows, aggregate bookings by city, date, and cab type.

Exploratory Analysis (Excel)
Use pivot tables and charts to understand trends and validate dataset quality.

Dashboard Creation (Power BI)
Load cleaned data, design interactive dashboards, and create DAX measures.

**Outcome**

This dashboard allows stakeholders to:

Quickly identify booking patterns and trends
Understand cancellation behavior with percentage metrics
Make data-driven operational and business decisions.

![Dashboard Screenshot](./screenshots/dashboard1.png)
