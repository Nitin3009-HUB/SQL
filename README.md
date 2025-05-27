# Capstone Project: Airline Operations & Customer Insights with SQL

# Situation: Leveraged a real-time flight operations database containing comprehensive flight, ticket, airport, and schedule data to perform critical operational and customer-centric analyses.

# Task: To address specific business questions by extracting, transforming, and analyzing complex relational data. Key analytical tasks included:

Identifying unique flights with the highest aircraft range.
Determining the details of the longest flights by duration.
Quantifying data inconsistencies by counting tickets without corresponding boarding passes.
Standardizing and reformatting booking dates for reporting.
Pinpointing month-wise highest-paying passengers for loyalty and marketing initiatives.

# Action:
I developed a suite of robust SQL queries, demonstrating proficiency in data manipulation and advanced analytical techniques:
Highest Range Flights: Utilized JOIN operations between flights and aircrafts tables to link flights to their aircraft models' ranges. Employed ORDER BY and LIMIT (or RANK() window function for handling ties) to identify the top flight(s) with the maximum operational range.
Longest Flight Details: Calculated flight durations by subtracting scheduled_departure from scheduled_arrival within the flights table. Applied ORDER BY on the calculated duration (descending) and LIMIT 1 (or RANK() for ties) to pinpoint the single longest flight and its associated details (flight number, departure/arrival airports, aircraft code).
Tickets Without Boarding Passes: Performed a LEFT JOIN from the tickets table to the boarding_passes table. Filtered results using a WHERE clause (bp.ticket_no IS NULL) to accurately count tickets that lacked an associated boarding pass, highlighting potential operational gaps or data discrepancies.
Booking Date Reformatting: Applied database-specific date formatting functions (e.g., TO_CHAR for PostgreSQL, DATE_FORMAT for MySQL, FORMAT for SQL Server) to transform the book_date column in the Bookings table into a consistent 'yyyy-mm-dd' string format, ensuring precise output column sequence.
Month-wise Top Spenders: Joined bookings and tickets tables to link transaction amounts and dates with passenger details. Employed SUM() with GROUP BY to aggregate total spending per passenger per month. Crucially, utilized the RANK() window function with PARTITION BY (month/year) and ORDER BY (total amount descending) to identify and retrieve the highest-paying passenger(s) for each respective month, ensuring accurate month-year formatting in the output.

# Result (Key Insights & Learning Outcomes):
This project significantly enhanced my practical SQL skills, enabling me to:
Extract Actionable Business Insights: Identified critical operational data (longest routes, high-range aircraft) for potential route optimization and resource allocation.
Improve Data Quality & Validation: Developed queries to detect and quantify data inconsistencies (e.g., un-boarded tickets), which is vital for maintaining database integrity and improving operational processes.
Enhance Customer Understanding: Pinpointed top-spending customers on a monthly basis, providing valuable data for targeted marketing campaigns, loyalty programs, and personalized service initiatives.
Master Data Transformation for Reporting: Gained expertise in reformatting and presenting data in user-friendly formats suitable for business stakeholders and analytical reports.
Develop Robust Querying Skills: Solidified my ability to write complex, multi-table queries, effectively use aggregate and window functions, and apply conditional logic to solve real-world data challenges.

# Skills Applied:
SQL Querying (Advanced)
SQL Joins (INNER, LEFT)
Window Functions (RANK(), PARTITION BY, ORDER BY)
Date & Time Functions (formatting, arithmetic)
Aggregation & Grouping (SUM(), COUNT(), GROUP BY)
Data Transformation & Formatting
Data Validation & Inconsistency Identification
Business Insight Extraction
Performance-Oriented Query Writing
Logical & Structured Problem Solving
