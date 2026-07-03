
## 📊 Dataset Information
- **Source:** GUVI Capstone Project Dataset
- **Size:** 100,000 rows × 25 columns
- **Domain:** Food Delivery / E-Commerce


### Columns:
| Column | Description |
|---|---|
| Order_ID | Unique order identifier |
| Customer_ID | Unique customer identifier |
| Customer_Age | Age of customer |
| Customer_Gender | Gender of customer |
| City | Delivery city |
| Area | Delivery area |
| Restaurant_ID | Unique restaurant identifier |
| Restaurant_Name | Name of restaurant |
| Cuisine_Type | Type of cuisine ordered |
| Order_Date | Date of order |
| Delivery_Time_Min | Delivery time in minutes |
| Distance_km | Delivery distance |
| Order_Value | Order value in ₹ |
| Discount_Applied | Discount amount in ₹ |
| Final_Amount | Final amount paid |
| Payment_Mode | Payment method used |
| Order_Status | Delivered/Cancelled |
| Cancellation_Reason | Reason for cancellation |
| Delivery_Rating | Rating given to delivery |
| Restaurant_Rating | Rating given to restaurant |
| Profit_Margin | Profit margin ratio |

---

## 🧹 Data Cleaning Steps
1. Dropped `Order_Time` column (all values = 0)
2. Filled missing categorical values with mode
3. Filled missing numeric values with median
4. Derived `Final_Amount` = `Order_Value - Discount_Applied`
5. Removed cancelled orders with null Final_Amount
2586 rows dropped
6. Capped `Discount_Applied` to max of `Order_Value`
7. Fixed invalid ratings (capped at 5.0)
8. Fixed negative `Profit_Margin` values
9. Standardized text columns (strip + title case)
10. Converted dtypes (datetime, int, category)

**Final cleaned dataset: 97,414 rows**

---

## ⚙️ Feature Engineering
| Feature | Description |
|---|---|
| `is_weekend` | 1 if Weekend, 0 if Weekday |
| `Age_Group` | 18-25, 26-35, 36-50, 50+ |
| `Delivery_Performance` | Fast/On-time/Delayed |
| `Profit_Margin_Pct` | Profit margin in % |
| `Has_Discount` | 1 if discount applied |
| `Discount_Pct` | Discount % of order value |
| `Order_Month` | Month extracted from date |
| `Order_Year` | Year extracted from date |
| `Order_Day` | Day name from date |

---

## 📈 EDA Insights
1. **Order Value** → Most orders between ₹500-₹2000
2. **Top City** → Hyderabad has highest orders
3. **Top Cuisine** → Indian cuisine most ordered
4. **Weekend** → Higher orders on weekends
5. **Delivery Time** → Avg 124.99 mins
6. **Cancellation Rate** → 12.78%
7. **Top Cancellation Reason** → Not Applicable
8. **Payment Mode** → Card is most preferred
9. **Peak Hours** → Lunch and dinner time
10. **Revenue Peak** → Month 7 (July) highest revenue

---

## 🗄️ SQL Database
- **Database:** PostgreSQL
- **Table:** food_delivery
- **Rows:** 97,414
- **Connection:** SQLAlchemy + psycopg2

### Key SQL Queries:
1. Total Orders & Revenue
2. Top 5 Cities by Revenue
3. Top 5 Cuisines by Orders
4. Avg Delivery Time by City
5. Top 5 Restaurants by Orders
6. Monthly Revenue Trend
7. Payment Mode Preference
8. Cancellation Rate
9. Avg Rating by Cuisine
10. Cancellation Reasons

---

## 📊 Power BI Dashboard
### KPIs:
| KPI | Value |
|---|---|
| Total Orders | 97K |
| Total Revenue | ₹166M |
| Avg Order Value | ₹1.79K |
| Avg Delivery Time | 124.99 mins |
| Cancellation Rate | 12.78% |
| Avg Delivery Rating | 2.99 |
| Avg Profit Margin | 17.88% |

### Visuals:
- Monthly Revenue Trend (Line Chart)
- Top Cities by Orders (Bar Chart)
- Delivery Performance (Pie Chart)
- Cancellation Reasons (Bar Chart)
- Cuisine Type Analysis (Bar Chart)
- Payment Mode (Pie Chart)

### Filters/Slicers:
- City
- Cuisine Type
- Order Status
- Order Month

---

## 💡 Business Recommendations
1. **Hyderabad & Bangalore** → Focus marketing here
2. **Indian cuisine** → Most popular, expand options
3. **12.78% cancellation** → Investigate and reduce
4. **Avg delivery 124 mins** → Optimize logistics
5. **Weekend demand** → Deploy more delivery partners
6. **Card payments** → Offer card-specific discounts

---
