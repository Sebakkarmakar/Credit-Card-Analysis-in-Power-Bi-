# Credit-Card-Analysis-in-Power-Bi-
Credit card financial dashboard using Power BI: • Developed an interactive dashboard using transaction and customer data from a SQL database, to provide real-time insights.

Credit card financial dashboard using Power BI:

Screenshot:

<img width="873" height="490" alt="Screenshot 2026-05-24 172838" src="https://github.com/user-attachments/assets/0f683d1a-1b91-493e-b507-e292834cc0b8" />

<img width="884" height="491" alt="Screenshot 2026-05-24 172813" src="https://github.com/user-attachments/assets/c2015c6e-8342-419f-837d-b04872c2f2b8" />


Project Objective
To develop a comprehensive credit card weekly dashboard that provides real-time insights into key performance metrics and trends, enabling stakeholders to monitor and analyze credit card operations effectively.

 	Import data to SQL database 
 	 Prepare csv file
 	Create tables in SQL
 	import csv file into SQL

 	DAX Queries
AgeGroup = SWITCH(
TRUE(),
'public cust_detail'[customer_age] < 30, "20-30",
'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40",
'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50",
'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60",
'public cust_detail'[customer_age] >= 60, "60+",
"unknown"
)

IncomeGroup = SWITCH(
TRUE(),
'public cust_detail'[income] < 35000, "Low",
'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] <70000, "Med",
'public cust_detail'[income] >= 70000, "High",
"unknown"
)

Project Insights

Overall revenue is 57M
•
Total interest is 8M
•
Total transaction amount is 46M
•
Male customers are contributing more in revenue 31M, female 26M
•
Blue & Silver credit card are contributing to 93% of overall transactions
•
TX, NY & CA is contributing to 68%
•
Overall Activation rate is 57.5%
•
Overall Delinquent rate is 6.06%
