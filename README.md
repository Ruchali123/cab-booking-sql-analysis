# 🚖 Cab Booking System – SQL Data Analysis

## 📌 Project Overview
This project simulates a **Cab Booking System** and performs **SQL-based data analysis** on customers, drivers, trips, bookings, and feedback.  
The goal is to derive insights into **customer behavior, driver performance, revenue trends, and operational efficiency**.

## 🗂️ Database Schema
The database contains the following tables:
- **Customers** – Customer details (ID, name, email, phone, gender, join date).
- **Drivers** – Driver details (ID, name, license, rating, join date).
- **Cabs** – Cab details (ID, model, number, capacity, type).
- **Bookings** – Booking details (pickup, drop, date, status).
- **TripDetails** – Trip distance, duration, fare, and payment mode.
- **Feedback** – Customer feedback with ratings and comments.

## 📊 Key Analysis Performed
1. **Customer Insights**
   - Most frequent customers by completed bookings.
   - Customers with high cancellation rates (>30%).
   - Retention analysis based on last booking date.

2. **Driver Performance**
   - Drivers with low ratings (<3.0).
   - Top 5 drivers by longest trips.
   - Drivers with high cancellation rates.

3. **Revenue & Business Metrics**
   - Total revenue in the last 6 months.
   - Top 3 most traveled routes.
   - Correlation between driver ratings and earnings.
   - Short vs long trip contribution to revenue.
   - Revenue comparison between *Tata Indica* and *Maruti Dzire*.

4. **Operational Efficiency**
   - Average travel time by pickup location.
   - Reasons for trip cancellations.
   - Weekend vs weekday booking patterns.

## 📂 Dataset
The dataset is provided in **csv format** (`cabs.csv, customer.csv, drivers.csv, tripdetails.csv`).  
You can load it into the database using:

### Option 1: **Import Wizard (Recommended)**
- In **MySQL Workbench**:  
  - `Server → Data Import → Import from Self-Contained File → Select XML/csv → Start Import`.  
- Or convert XML → CSV in Excel → Import with **Table Data Import Wizard**.

### Option 2: **Manual Loading**
Use `LOAD XML INFILE` (requires XML structure matching the table schema).  

Example:
```sql
LOAD XML INFILE 'cab_booking_data.xml'
INTO TABLE Customers
ROWS IDENTIFIED BY '<Customer>';
