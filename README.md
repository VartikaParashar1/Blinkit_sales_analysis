# **Blinkit Sales Analytics Dashboard**

This project demonstrates a **Power BI Sales Analytics Dashboard** for Blinkit, "India's Last Minute App." It offers interactive visualizations and detailed insights into sales performance, outlet-wise contributions, and product-level trends to support data-driven decision-making.

---

## **Overview**

The Blinkit Sales Analytics Dashboard provides actionable insights into key sales metrics, helping stakeholders monitor performance and optimize business strategies. By analyzing trends in sales, outlet performance, and product categories, this project enables effective decision-making for growth and customer satisfaction.

---

## **Features**

1. **Interactive Dashboard**:
   - Filters for Outlet Location Type, Outlet Size, and Item Type.
   - Dynamic visualizations to analyze key metrics.

2. **Visualized Metrics**:
   - **Total Sales**: Tracks overall sales performance.
   - **Average Sales**: Measures sales efficiency across outlets.
   - **Number of Items Sold**: Evaluates product-level contributions.
   - **Average Ratings**: Tracks customer satisfaction by product.

3. **Visualizations**:
   - Donut charts for fat content and outlet size contributions.
   - Bar charts for item performance and outlet sales.
   - Line charts for outlet establishment trends over time.

---

## **Key Insights**

- **Total Sales**: $1.20M with an average sale of $141.
- **Highest Performing Outlets**: Tier 3 locations with $472.13K sales.
- **Top Product Categories**: Fruits and Snacks contribute $0.18M each.
- **Outlet Size Performance**: Medium-sized outlets lead with $507.90K.

---

## **MySQL Queries**

Below are the SQL queries used to generate the dataset for this dashboard:

### **1. Total Sales**
```sql
SELECT 
    SUM(sales_amount) AS total_sales,
    AVG(sales_amount) AS avg_sales,
    COUNT(item_id) AS total_items,
    AVG(rating) AS avg_rating
FROM sales_data;
```

### **2. Sales by Outlet Location**
```sql
SELECT 
    outlet_location_type,
    SUM(sales_amount) AS total_sales
FROM sales_data
GROUP BY outlet_location_type;
```

### **3. Sales by Outlet Size**
```sql
SELECT 
    outlet_size,
    SUM(sales_amount) AS total_sales
FROM sales_data
GROUP BY outlet_size;
```

### **4. Sales by Item Type**
```sql
SELECT 
    item_type,
    SUM(sales_amount) AS total_sales
FROM sales_data
GROUP BY item_type
ORDER BY total_sales DESC;
```

### **5. Outlet Establishment Trends**
```sql
SELECT 
    YEAR(establishment_year) AS year,
    SUM(sales_amount) AS total_sales
FROM sales_data
GROUP BY YEAR(establishment_year)
ORDER BY year ASC;
```

### **6. Fat Content by Outlet**
```sql
SELECT 
    outlet_location_type,
    fat_content,
    SUM(sales_amount) AS total_sales
FROM sales_data
GROUP BY outlet_location_type, fat_content;
```

### **7. Outlet Performance Summary**
```sql
SELECT 
    outlet_type,
    SUM(sales_amount) AS total_sales,
    COUNT(item_id) AS no_of_items,
    AVG(sales_amount) AS avg_sales,
    AVG(rating) AS avg_rating
FROM sales_data
GROUP BY outlet_type;
```

### **8. Top Performing Items**
```sql
SELECT 
    item_type,
    SUM(sales_amount) AS total_sales,
    COUNT(item_id) AS total_items
FROM sales_data
GROUP BY item_type
ORDER BY total_sales DESC
LIMIT 10;
```

### **9. Sales by Fat Content**
```sql
SELECT 
    fat_content,
    SUM(sales_amount) AS total_sales
FROM sales_data
GROUP BY fat_content;
```

---

## **Getting Started**

### **Prerequisites**
To view or edit the dashboard, ensure you have the following:
- **Power BI Desktop**: [Blinkit dashboard](https://powerbi.microsoft.com/)
- The `.pbix` file available in this repository.
- Access to the database used for this project.

---

## **Usage**

1. Use the filter panel to:
   - Analyze sales by outlet location type (Tier 1, Tier 2, Tier 3).
   - Compare performance based on outlet size.
   - Drill down into item-level sales data.
2. Review trends in outlet establishment and sales growth over time.
3. Identify top-performing products and focus on customer preferences.

---








