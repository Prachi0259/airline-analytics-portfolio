# ✈️ Airline Analytics Portfolio Project

> **SQL-based analysis of 51,582 US domestic flights — uncovering delay patterns, route performance, and airline rankings.**

---

## 👩‍💻 About the Project

This project performs an in-depth analysis of the **2015 US Domestic Flights Dataset** using **MySQL**. It explores airline performance, delay trends, busiest routes, and worst-performing airports through a series of carefully crafted SQL queries — ranging from basic aggregations to advanced CTEs and Window Functions.

The results are presented in an interactive **HTML portfolio dashboard** built from scratch.

---

## 📊 Dataset

| File | Description | Rows |
|------|-------------|------|
| `flights.csv` | Flight records with delay, distance, time info | 51,582 |
| `airlines.csv` | Airline IATA codes and names | 14 |
| `airports.csv` | Airport codes, cities, states, coordinates | 319 |
| `cancellation_codes.csv` | Cancellation reason codes | 4 |

**Source:** [Kaggle — 2015 Flight Delays and Cancellations](https://www.kaggle.com/datasets/usdot/flight-delays)

---

## 🔍 Key Findings

- 🥇 **Virgin America** has the best on-time rate at **63.9%** despite flying the longest average routes (1,485 miles)
- 🔴 **Frontier Airlines** is the worst performer with **30.46 min** average arrival delay
- ✈️ **JFK → LAX** is the busiest US domestic route
- 🏙️ **LAX** appears in 6 of the top 10 busiest routes
- 📅 **Friday** is the worst day to fly — 9.84 min avg delay
- 📅 **Saturday** is the best day — only 5.46 min avg delay
- 🏢 **DFW (Dallas)** is the worst departure airport with 32.62 min avg delay
- 🤠 **Houston has TWO airports** in the top 10 worst — HOU and IAH

---

## 🛠️ SQL Techniques Used

| Query | Technique |
|-------|-----------|
| Flights per airline | `JOIN`, `GROUP BY`, `ORDER BY` |
| Avg delay per airline | `AVG()`, `ROUND()` |
| Busiest routes | Double `JOIN` on same table |
| Delays by day | `CASE WHEN` |
| Worst airports | `HAVING` clause |
| Airline scorecard | Multiple aggregations |
| Performance ranking | `CTE` + `RANK()` Window Function |

---

## 📁 Project Structure

```
airline-analytics/
│
├── data/
│   ├── airlines.csv
│   ├── airports.csv
│   ├── cancellation_codes.csv
│   └── flights.csv
│
├── queries/
│   ├── 01_flights_per_airline.sql
│   ├── 02_avg_delay_per_airline.sql
│   ├── 03_busiest_routes.sql
│   ├── 04_delays_by_day.sql
│   ├── 05_worst_airports.sql
│   ├── 06_airline_scorecard.sql
│   └── 07_performance_ranking_cte.sql
│
├── dashboard/
│   └── airline_analytics_portfolio.html
│
└── README.md
```

---

## 🚀 How to Run

### 1. Set up the database
```sql
CREATE DATABASE flight_analysis;
USE flight_analysis;
```

### 2. Import the CSV files
Use **MySQL Workbench → Table Data Import Wizard** to import:
- `airlines.csv`
- `airports.csv`
- `flights.csv`

For `cancellation_codes.csv`, run manually:
```sql
CREATE TABLE cancellation_codes (
    CANCELLATION_REASON VARCHAR(1),
    CANCELLATION_DESCRIPTION VARCHAR(50)
);
INSERT INTO cancellation_codes VALUES
('A', 'Airline/Carrier'),
('B', 'Weather'),
('C', 'National Air System'),
('D', 'Security');
```

### 3. Run the queries
Open any `.sql` file from the `queries/` folder in MySQL Workbench and execute.

### 4. View the dashboard
Open `dashboard/airline_analytics_portfolio.html` in any browser.

---

## 📸 Dashboard Preview

> Interactive dashboard with charts, SQL viewer, and key insights.
> Open `airline_analytics_portfolio.html` in your browser to explore.

---

## 🧰 Tools Used

- **MySQL Workbench** — Database setup & query execution
- **SQL** — Data analysis (JOINs, CTEs, Window Functions)
- **HTML / CSS / JavaScript** — Portfolio dashboard
- **Google Colab** — Data exploration

---

## 📬 Contact

**Prachi**
- 📧 [prachi7.work@gmail.com](mailto:prachi7.work@gmail.com)
- 💼 [linkedin.com/in/prachi252](https://www.linkedin.com/in/prachi252/)
- 🐙 [github.com/Prachi0259](https://github.com/Prachi0259)

---

*Built with 💙 using real flight data and pure SQL*
