 Sunrise Supermarket
 * Student Name: Queen Ineza
 * Student ID: 29354
 * DBMS Used: SQL Plus
 Business Scenario

Sunrise Supermarket maintains a relational database to record customer purchases, order histories, and product inventories. To help management analyze customer demographics, purchasing behavior, and sales trends over time, advanced SQL querying techniques were implemented on tables covering customers, products, categories, orders, and order items.

 Queries 
 
 * Customer Spending Rank
   * Objective: Rank customers by their overall expenditure using analytical window functions.
   * Implementation: Calculates total spending per customer via aggregate functions, then applies the RANK() window function ordered by total revenue in descending order.
 * Running Total of Revenue
   * Objective: Track cumulative revenue growth sequentially across order dates.
   * Implementation: Employs the SUM() function configured as a window aggregate combined with an OVER (ORDER BY order_date ASC) clause.
 * Days Between Current and Previous Order
   * Objective: Measure the time intervals between consecutive orders for returning customers.
   * Implementation: Utilizes a Common Table Expression (CTE) alongside the LAG() window function to retrieve prior order timestamps, filtered specifically for customers who have placed multiple orders.

     <img width="881" height="441" alt="Screenshot 2026-09-21 130007" src="https://github.com/user-attachments/assets/63ad7ec4-c6d9-43bc-a4f0-034117d79d5f" />
     <img width="640" height="297" alt="Screenshot 2026-09-21 125302" src="https://github.com/user-attachments/assets/bc3f8286-bab0-48eb-ab26-f67ad1da391a" />
<img width="1052" height="495" alt="Screenshot 2026-09-21 125509" src="https://github.com/user-attachments/assets/fd96f382-9764-4086-a18f-80067e2a8e8b" />

 Business Insights & Interpretation
 * Customer Loyalty: Monitoring order intervals through date-gap analysis highlights engagement patterns and helps pinpoint repeat buyers.
 * Sales Momentum: Evaluating cumulative revenue streams enables management to assess long-term financial growth and business performance effectively.. Challenges & Resolution
    Handling missing table/column references (such as direct revenue columns). Resolution: Used table joins across orders, order_items, and products to properly calculate revenue on the fly.
