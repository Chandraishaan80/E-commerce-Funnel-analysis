# DAX Measures Used

This file contains DAX measures used in the Power BI dashboard for analyzing delivery performance, customer satisfaction, and order funnel behavior.

---

## 📊 Customer Satisfaction

### Average Review Score

Avg Review Score =
AVERAGE(olist_order_reviews_dataset[review_score])

---

### Total Bad Reviews

Total Bad Reviews =
SUM(olist_order_reviews_dataset[bad_review])

---

## 🚚 Delivery Performance

### Average Delivery Time

Avg Delivery Time =
AVERAGE(olist_orders_dataset[delivery_time])

---

### Late Delivery Rate

Late Delivery Rate =
AVERAGE(olist_orders_dataset[is_late])

---

## 📦 Orders & Funnel

### Total Orders

Total Orders =
COUNTROWS(olist_orders_dataset)

---

### Delivered Orders

Delivered Orders =
CALCULATE(
COUNTROWS(olist_orders_dataset),
olist_orders_dataset[order_status] = "delivered"
)

---

### Order Completion Rate

Order Completion Rate =
DIVIDE([Delivered Orders], [Total Orders])

---

## 📉 Funnel Analysis Support

### Orders by Status

Orders by Status =
COUNTROWS(olist_orders_dataset)

---

## 🧠 Key Insights Enabled

* Compared customer ratings based on delivery delays (`is_late`)
* Evaluated delivery efficiency using average delivery time
* Identified proportion of bad reviews using binary flag
* Analyzed order funnel drop-offs across different statuses
