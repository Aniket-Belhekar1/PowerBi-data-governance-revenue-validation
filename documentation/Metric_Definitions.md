Certified Metric #1 — REVENUE

Attribute:	Value
Metric Name:	Revenue
Business Definition:	Net revenue generated from completed customer orders
Included Orders:	Order Status = Completed
Excluded Orders:	Cancelled, Returned
Revenue Type:	Net
Formula:	Sales – (Sales × Discount)
Grain:	Order line (Row ID)
Time Dimension:	Order Date
Source Table:	orders_raw
Data Owner:	Business Finance
Metric Status:	Certified

Certified Metric #2 — Orders Count	
	
Attribute:	Value
Metric Name:	Orders Count
Business Definition:	Number of unique completed customer orders
Included Orders:	Order Status = Completed
Formula:	DISTINCTCOUNT(Order ID)
Grain:	Order
Source Table:	orders_raw
Metric Status":	Certified

Certified Metric #3 — Active Customers	
	
Attribute:	Value
Metric Name:	Active Customers
Business Definition:	Customers who placed at least one completed order
Formula:	DISTINCTCOUNT(Customer ID)
Filter Condition:	Order Status = Completed
Grain:	Customer
Source Table":	orders_raw
Metric Status:	Certified

Certified Metric #4 — Average Order Value (AOV)	
	
Attribute:	Value
Metric Name:	Average Order Value
Business Definition:	Average revenue per completed order
Formula:	Revenue ÷ Orders Count
Dependency:	Revenue, Orders Count
Metric Status:	Certified


