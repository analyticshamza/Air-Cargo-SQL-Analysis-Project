# ✈️ Air Cargo SQL Analysis Project

This SQL project analyzes air cargo and passenger data using a relational database approach. It involves creating a normalized schema, importing data from CSVs, writing queries for various analytical use cases, and implementing advanced SQL features such as indexing, views, and stored procedures.

---

## 📁 Project Structure

```

📦 air-cargo-sql-analysis/
├── aircargo.txt                 # SQL script to create tables and foreign keys
├── customer.csv                 # CSV data for customer table
├── routes.csv                   # CSV data for routes table
├── passengers\_on\_flights.csv   # CSV data for passengers on flights table
├── ticket\_details.csv          # CSV data for ticket details table
├── aircargo.png                # ER Diagram of the database schema
├── Air\_Cargo\_Analysis\_Project.pdf  # Report with SQL query tasks and outputs
└── README.md                   # Project description and instructions (this file)

````

---

## 🏗️ Setup Instructions

### 1. Create the Database and Tables

- Open MySQL Workbench.
- Create a new connection and run the SQL script:

```sql
source aircargo.txt;
````

This script:

* Creates the `AirCargo` database
* Creates all 5 tables
* Sets up primary and foreign keys
* Adds `AUTO_INCREMENT` to `ticket_id`

---

### 2. Import Data

Import the `.csv` files into the respective tables using MySQL Workbench or any other tool:

| Table                   | CSV File                    |
| ----------------------- | --------------------------- |
| `customer`              | `customer.csv`              |
| `routes`                | `routes.csv`                |
| `passengers_on_flights` | `passengers_on_flights.csv` |
| `ticket_details`        | `ticket_details.csv`        |

**Note:** The `aircraft` table is populated using this query, which extracts unique aircraft IDs from the `routes` table:

```sql
INSERT INTO aircraft (aircraft_id)
SELECT DISTINCT aircraft_id FROM routes;

---

## 🗃️ ER Diagram

![Image](https://github.com/user-attachments/assets/12a2ebc2-c32c-48ae-9341-246ebd24801c)

---

## ✅ SQL Tasks Covered

The project includes solutions to the following tasks:

1. Create the database and import data
2. Design the ER diagram
3. Filter passengers by route ID
4. Calculate business class revenue
5. Display customer full names
6. Join customers who booked tickets
7. Filter by customer ID and brand (e.g., Emirates)
8. Subquery for Economy Plus travelers
9. Use IF clause to check revenue > 10,000
10. Create and grant privileges to a new user
11. Use window functions for max ticket price
12. Add index to optimize query by route ID
13. Use `EXPLAIN` to view query execution plan
14. Use `ROLLUP` to calculate ticket price totals
15. Create a view for business class passengers
16. Create a stored procedure for routes > 2000 miles
17. Use `GROUP BY` to count tickets and total cost per customer
18. Calculate average number of passengers per route

All tasks and outputs are documented in [`Air_Cargo_Analysis_Project.pdf`].

---

## 🧠 Technology Used

* MySQL Workbench
* dbdiagram.io (for ER diagram)
* CSV data imports
* SQL features: `JOIN`, `GROUP BY`, `ROLLUP`, `VIEW`, `PROCEDURE`, `INDEX`, `EXPLAIN`, `GRANT`, `REVOKE`

---

## 📄 License

This project is licensed under the [MIT License]
