# 🍕 Pizza Sales Analysis – Power BI Project

## 📌 Problem Statement

The objective of this project is to analyze pizza sales data and derive actionable insights to understand business performance and customer behavior. The client required a dashboard to track **key performance indicators (KPIs)** and visualize patterns across orders, revenue, and product categories.

The KPIs defined were:

1. **Total Revenue** – Total sales amount from all orders.
2. **Average Order Value (AOV)** – Revenue divided by number of orders.
3. **Total Pizzas Sold** – Total quantity of pizzas sold.
4. **Total Orders** – Total number of customer orders.
5. **Average Pizzas per Order** – Total pizzas sold divided by total orders.

---

## 🛠️ Work Done

### 🔹 Data Transformation (SQL)

* Cleaned and formatted raw sales data using **SQL**, including correcting date formats with `STR_TO_DATE()`.
* Verified and validated data consistency by checking unique values and duplicates.
* Derived preliminary insights using SQL queries before visualization.

### 🔹 Data Preparation (Power BI / Power Query)

* Imported SQL-transformed data into Power BI.
* Verified **unique keys** like `pizza_id`.
* Corrected **data types** for accurate aggregation.
* Added calculated columns and transformations:

  * **Weekday column**: `FORMAT('sql_pizza_sales'[order_date], "dddd")`
  * **Measures** for KPIs, e.g.:

```DAX
Average Order Value = 
DIVIDE(
    SUMX(sql_pizza_sales, sql_pizza_sales[quantity] * sql_pizza_sales[unit_price]),
    DISTINCTCOUNT(sql_pizza_sales[order_id])
)
```

* Built multiple **visualizations and interactive filters** to analyze sales performance.

---

## 📊 Dashboard Overview

### **Dashboard 1 – Sales Performance & Trends**

* KPIs at the top for quick performance tracking.
* **Orders by Weekday**: Friday and Thursday are peak order days, while Sunday records the lowest.
* **Orders by Month**: Seasonal spikes in **July & August**, with dips in February and October.
* **Sales by Category**:

  * Classic pizzas dominate (26.9% share).
  * Chicken, Veggie, and Supreme categories contribute fairly evenly (\~23–25%).
* **Sales by Size**:

  * Large pizzas are most popular (**45.9% of sales**), followed by Medium (30.5%).
  * XXL pizzas have negligible demand (1.7%).

### **Dashboard 2 – Product Insights**

* **Top Pizzas by Revenue**:

  * *Thai Chicken Pizza* and *Barbecue Chicken Pizza* lead with \~\$43K sales each.
  * *Classic Deluxe* and *California Chicken* are also strong performers.
* **Top Pizzas by Quantity Sold**:

  * *Classic Deluxe Pizza* tops in volume (\~2.5K sold).
  * Chicken and Hawaiian pizzas also sell in high numbers.
* **Bottom Pizzas by Revenue**:

  * *Spinach Pesto Pizza* and *Mediterranean Pizza* generate lowest sales (\~15K).
  * *Brie Carre Pizza* performs the worst (\~11.6K).
* **Bottom Pizzas by Quantity Sold**:

  * *Brie Carre Pizza* has the lowest demand (\~490 units).
  * Other low performers include *Calabrese*, *Mediterranean*, and *Spinach Supreme*.

---

## 🔑 Key Insights

1. **High reliance on Classic & Chicken pizzas** – They dominate both sales and orders.
2. **Large-sized pizzas are the most profitable** – Suggests customers prefer value-for-money portions.
3. **Friday is the busiest day** – Marketing promotions should target weekends.
4. **Seasonal demand exists** – Sales peak in summer months (July–August).
5. **Underperforming pizzas (Spinach, Brie Carre, Mediterranean)** – May need recipe tweaks, bundling, or removal.

---

## 📌 Tools & Technologies

* **SQL** – Data cleaning & transformation
* **Power BI / Power Query** – Data modeling & dashboarding
* **DAX** – KPI and measure calculations

---

## 📷 Dashboards

### Dashboard 1 – KPIs, Trends, Category & Size Analysis

![Dashboard 1](<img width="1177" height="664" alt="image" src="https://github.com/user-attachments/assets/41dc1f3f-b335-47ac-80f1-cf5e8ab9b6e4" />
)
<img width="1177" height="664" alt="image" src="https://github.com/user-attachments/assets/96502ad9-af2e-4e2f-bff4-8ff75c886a7e" />


### Dashboard 2 – Top & Bottom Pizza Performance

![Dashboard 2](<img width="1176" height="657" alt="image" src="https://github.com/user-attachments/assets/ba1fee90-6150-4622-b9fc-508ec50ef563" />
)

---

## 🚀 Conclusion

This analysis provides a **comprehensive view of sales performance**, helping decision-makers identify top-performing products, seasonal demand patterns, and underperforming items. With these insights, the business can optimize its menu, focus on high-demand categories, and strategically plan promotions.

