# Setup — read this before Day 1

You only need a spreadsheet tool and a SQLite viewer. Nothing is paid.

## 1. Clone the repo
```bash
git clone <your-repo-url>
cd foodco-bootcamp
```
Each morning: `cd` into that day's folder and open `instructions.md`.

## 2. Modules 1–2 (Days 1–6): Excel / Google Sheets
- **Microsoft Excel** (2016+, or Microsoft 365) — needed for **Power Query** (Day 3), **Pivot Tables** (Day 5) and **Macros/VBA** (Day 6).
  - Enable the Developer tab (Day 6): *File ▸ Options ▸ Customize Ribbon ▸ tick **Developer***.
- **Google Sheets** works for Days 1–2 and basic lookups, but Power Query and VBA macros are Excel-only. If you're on Mac/Chromebook, a free [Excel for the web](https://office.com) account covers most of it (VBA recording is limited — pair up with a Windows user on Day 6).

## 3. Module 3 (Days 7–10): SQL
Pick **one**. Option A is the zero-setup default.

### Option A — DB Browser for SQLite (recommended, no server)
1. Download **DB Browser for SQLite** (free): https://sqlitebrowser.org
2. Open it ▸ *Open Database* ▸ select `datasets/foodco.db`.
3. Go to the **Execute SQL** tab, type your query, press ▶ (F5).

### Option B — PostgreSQL or MySQL (for students who want the "real" stack)
1. Create an empty database.
2. Run `datasets/schema.sql` to create the tables.
3. Import the CSVs from `datasets/` into the matching tables:
   - **PostgreSQL:** `\copy customers FROM 'datasets/customers.csv' CSV HEADER;` (repeat per table — load `customers, restaurants, delivery_partners, menu_items, orders, order_items, payments` in that order so foreign keys resolve).
   - **MySQL:** `LOAD DATA INFILE ... FIELDS TERMINATED BY ',' IGNORE 1 LINES;`

### Option C — Python + SQLAlchemy (optional, for the keen)
```python
import sqlalchemy as sa, pandas as pd
engine = sa.create_engine("sqlite:///datasets/foodco.db")
pd.read_sql("SELECT city, COUNT(*) FROM orders GROUP BY city", engine)
```

## 4. (Optional) Regenerate the data yourself
The entire dataset is produced by one seeded script:
```bash
python datasets/generate_data.py
```
Requires Python 3.9+ and `pandas`. Re-running gives identical data (seed = 42).

## 5. Day 10 BI bonus
Power BI Desktop (free, Windows) or Tableau Public (free) can both connect to a SQLite database via an ODBC driver, or to the exported CSVs directly. Instructions are in `Day_10_CTE_Reporting_Capstone/instructions.md`.
