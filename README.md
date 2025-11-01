#  E-commerce Fulfillment Performance Analysis

This project demonstrates an **end-to-end data cleaning, transformation, and analysis** workflow using **Microsoft Excel and Power Query** for an e-commerce business.

---

##  Overview

The goal of this analysis is to evaluate **order fulfillment efficiency**, understand how **logistics impact profitability**, and identify **patterns in returns and delivery delays**.

Key performance indicators (KPIs) visualized include:
-  Total Sales  
-  Payment Methods  
-  Regional Sales  
-  Delivery Days per Carrier  
-  Return Rate & Refund Value  
-  Daily Sales Trend  

---

##  Dataset Overview

The dataset includes **five tables** representing different aspects of business operations:

| Table | Description |
|-------|--------------|
| Customers | Customer details, regions, and loyalty tiers |
| Products | Product IDs, names, categories, and cost/selling prices |
| Orders | Sales transactions including discounts and payment types |
| Shipments | Order delivery performance by carrier |
| Returns | Returned orders and refund details |

---

##  1. Data Cleaning and Transformation (Power Query)

### **Customers Table**
- Standardized inconsistent region names (e.g., “south-east” → “South East”)
- Filled missing loyalty tiers with `"Bronze"`
- Removed duplicate records based on `CustomerID`

### **Orders Table**
- Standardized date formats  
- Corrected typos in `PaymentType` (e.g., “Cedit Card” → “Credit Card”)  
- Replaced missing discounts with 0  
- Removed duplicate order entries  

### **Products Table**
- Replaced missing `CostPrice` for 11 products using category-based average markup  
- Ensured all cost and selling prices are numeric  
- Verified unique `ProductID` values  

### **Shipments Table**
- Standardized carrier names (`DPD`, `DHL`, `Hermes`, `Royal Mail`)  
- Fixed negative or null delivery days using median per carrier  

### **Returns Table**
- Ensured returned order IDs matched valid order IDs  
- Converted refund values to currency format  

---

##  2. Data Integration

Using Power Query:
- Merged all tables using **Left Joins** on key columns (`CustomerID`, `ProductID`, `OrderID`)
- Created a single **Master Table** ready for reporting
- Loaded the cleaned dataset into Excel for analysis (`Close & Load`)

---

##  3. Dashboard & Analysis

<img width="1209" height="536" alt="eCommerceDashboard" src="https://github.com/user-attachments/assets/01fdcab7-9247-400d-9539-f1bb244b69a3" />

<img width="1205" height="513" alt="eCommerce2 0" src="https://github.com/user-attachments/assets/ac9548af-4fb4-443d-a88c-2b90c0a61d92" />



### **Dashboard Highlights**
| Metric | Insight |
|--------|----------|
| **Total Sales** | £181,475 |
| **Average Sale** | £4,537 |
| **Return Rate** | 0.51% |
| **Total Refunds** | £923.77 |
| **Top Payment Method** | Credit Card (£57,458) |
| **Top Region** | London (£50,423) |
| **Best-Selling Product** | PROD336 |
| **Most Profitable Product** | PROD336 |
| **Least Average Delivery Days by Carrier** | DHL (3.36 Average Days) |

### **Key Insights**
- **London** and **Credit Card** payments drive the majority of sales.  
- **Royal Mail** and **DPD** handled most deliveries, though **DHL** showed the fastest average delivery time.  
- **Returns and refunds** were minimal (<1%), indicating strong fulfillment accuracy.  
- Sales peaked in late January and mid-February — possible promotional or marketing periods.  

---

##  4. Analytical Recommendations

1. **Optimize delivery operations** by studying why Royal Mail handles more orders but with longer delivery times.  
2. **Increase promotions in Midlands and South East** to balance regional sales performance.  
3. **Encourage faster payment methods** like Debit/Credit cards to speed transaction cycles.  
4. **Monitor return patterns** — especially for specific SKUs or regions.  

---

##  Tools Used

- **Microsoft Excel** (PivotTables, Charts, Dashboard Design)
- **Power Query** (Data Cleaning & Transformation)
- **XLOOKUP** (CostPrice mapping)
- **Power Pivot** (Model relationships and DAX measures)

---

##  Repository Structure

