🍕 Pizza Sales Analysis

This project performs a comprehensive analysis of pizza sales data, uncovering insights on top-selling pizzas, peak order times, pricing strategy, customer preferences, and profitability trends. It uses Python (Pandas + SQLAlchemy) with SQLite for structured data analysis and logging for transparency.

📊 Overview

The analysis focuses on six key business insights:

Top 10 Best-Selling Pizzas

Customer Behavior & Peak Hours

Pricing Strategy by Pizza Size

Menu Customization & Dietary Trends

Profitability Monitoring (Revenue, Cost, Margin)

Category-Wise Demand Insights

📁 Datasets Used

The project uses four CSV files:

File Name	Description
orders.csv	Contains order timestamps (date and time).
order_details.csv	Tracks each item in an order and its quantity.
pizzas.csv	Contains pizza IDs, sizes, and prices.
pizza_types.csv	Contains pizza names, categories, and ingredients.

All files are read, cleaned, and inserted into a local SQLite database (pizza.db).

⚙️ Features

Reads multiple CSV datasets and loads them into SQLite.

Logs all major steps using Python’s logging module.

Performs analytical SQL queries to find:

Most popular pizzas.

Busiest days and hours.

Revenue and profitability by category and size.

Vegetarian vs Non-Vegetarian distribution.

Detects loss-making pizzas based on cost assumptions.

🧠 Key Insights

Top Pizza: Classic Deluxe

Busiest Day: Friday

Peak Hour: 12 PM

Most Popular Size: Large (L)

Highest Margin Category: Vegetarian pizzas

Low-margin Items: Certain non-veg pizzas (e.g., with chicken or bacon)

🧩 Tech Stack
Component	Description
Language	Python 3
Libraries	pandas, sqlalchemy, logging, warnings, time
Database	SQLite
Environment	Google Colab / Local Python Environment
🧱 Project Structure
📦 pizza-sales-analysis
 ┣ 📜 untitled4.py                # Main analysis script
 ┣ 📊 order_details.csv
 ┣ 📊 orders.csv
 ┣ 📊 pizzas.csv
 ┣ 📊 pizza_types.csv
 ┣ 🗃️ pizza.db                    # SQLite database (created automatically)
 ┣ 🧾 log_file.log                # Execution log
 ┗ 📘 README.md                   # Project documentation

🚀 How to Run
1️⃣ Install Required Libraries
pip install pandas sqlalchemy

2️⃣ Place CSV Files

Ensure these files are in the same directory as untitled4.py:

order_details.csv

orders.csv

pizzas.csv

pizza_types.csv

3️⃣ Run the Script
python untitled4.py


The script will:

Load data into SQLite

Log progress in log_file.log

Print key query outputs and insights

🧮 Example Queries

Some sample SQL queries from the project:

-- Top 10 best-selling pizzas
SELECT pizza_type_id, SUM(quantity) AS total_quantity
FROM order_details
JOIN pizzas ON order_details.pizza_id = pizzas.pizza_id
GROUP BY pizza_type_id
ORDER BY total_quantity DESC
LIMIT 10;

-- Busiest day of the week
SELECT strftime('%w', date) AS day_of_week, COUNT(*) AS total_order
FROM orders
GROUP BY day_of_week
ORDER BY total_order DESC;

🪵 Logging

All steps are logged with timestamps in log_file.log, including:

Data loading confirmation

Database insertion

Query execution

Any errors or missing files

🧾 Sample Output
Top 10 Best Pizzas:
1. classic_dlx
2. bbq_ckn
3. hawaiian
...

Busiest Day: Friday
Peak Hour: 12 PM
Most Popular Size: Large

💡 Future Enhancements

Interactive dashboard (using Power BI or Plotly)

Dynamic cost and profit tracking

Real-time data ingestion and updates

Customer segmentation analysis

👩‍💻 Author

Nikita
📫 Data Enthusiast | SQL & Python Analyst
