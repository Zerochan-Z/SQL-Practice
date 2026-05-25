# SQL-Practice
Data table learning 1.0 (ˉ﹃ˉ)

# 🗄️ SQL Command Reference

Quick lookup table for the SQL commands you used.

---

## 📌 Table Management

| Command | What it does |
|---------|--------------|
| `DROP TABLE IF EXISTS (name)` | Delete the whole table if it exists (no error if missing) |
| `CREATE TABLE (name) (\n  {column}  (Data type) \n)` | Create a new empty table |
| `Continue with comma (,) except the last` | Continue code writing |
| `After ) write ;` | End code writing |

### Data Types

| Type | Meaning |
|------|---------|
| `INTEGER` | Whole number |
| `TEXT` | String (text) |
| `REAL` | Decimal number |
| `PRIMARY KEY` | Unique row identifier (only one per table) |

---

## 📥 Data Insertion

| Command | What it does |
|---------|--------------|
| `INSERT INTO (name) ({columns,}) VALUES \n ({datas})` | Add rows of data |
| `For text need to put '__'` | Turns text into str |

---
## 📁 SQL Notes – Quick Reference

| Clause / Concept | What It Does |
|-----------------|---------------|
| **SELECT all columns** | `*` means every column |
| **SELECT specific columns** | Choose which columns to show |
| **WHERE (filter rows)** | Filters rows before grouping (like an if‑clause) |
| **AND (multiple conditions)** | Adds another condition to `WHERE` |
| **AS (alias)** | Renames a column (applies only to the column immediately before it) |
| **LOWER()** | Converts text to lowercase |
| **GROUP BY** | Groups rows into categories; one row per unique combination |
| **SUM()** | Adds up all values in a group |
| **COUNT()** | Counts number of rows in a group |
| **AVG()** | Calculates average of values in a group |
| **HAVING** | Filters **groups** after `GROUP BY` (unlike `WHERE` which filters rows) |
| **ORDER BY** | Sorts results (DESC = highest first, ASC = lowest first) |
| **LIMIT** | Shows only first N rows (always at the end) |

---

## 📋 Formula Templates

| Task | Template |
|------|----------|
| Basic select | `SELECT {columns} FROM {table};` |
| Select with condition | `SELECT {columns} FROM {table} WHERE {column} = '{value}';` |
| Select with multiple conditions | `SELECT {columns} FROM {table} WHERE {condition1} AND {condition2};` |
| Group by with aggregate | `SELECT {group_column}, SUM({agg_column}) AS {alias} FROM {table} GROUP BY {group_column};` |
| Case‑insensitive grouping | `SELECT LOWER({column}) AS {alias}, AVG({agg_column}) FROM {table} GROUP BY LOWER({column});` |
| Filter after grouping | `SELECT {group_column}, COUNT(*) FROM {table} GROUP BY {group_column} HAVING COUNT(*) > {number};` |
| Top N results | `SELECT {columns} FROM {table} ORDER BY {column} DESC LIMIT {N};` |

---

## 🔄 Execution Order (How SQL Reads Your Query)

| Step | Clause | What happens |
|:----:|--------|--------------|
| 1 | `FROM` | Choose the table |
| 2 | `WHERE` | Filter rows (before grouping) |
| 3 | `GROUP BY` | Group rows into categories |
| 4 | `HAVING` | Filter groups (after grouping) |
| 5 | `SELECT` | Pick columns to show + calculate aggregates |
| 6 | `ORDER BY` | Sort the result |
| 7 | `LIMIT` | Cut off after N rows |

---

## ⚠️ Common Mistakes

| Mistake | Why It's Wrong |
|---------|----------------|
| `WHERE COUNT(*) > 1` | `WHERE` cannot use aggregates (use `HAVING` instead) |
| `SELECT ticker, price FROM trades GROUP BY ticker` | `price` is not in `GROUP BY` and not aggregated |
| `HAVING price > 200` | `HAVING` without aggregate works, but `WHERE` is better for row filters |
| Missing `AS` for alias | Works, but output column name will be `SUM(quantity)`
| Calculate sum | `SUM()` |
| Count rows | `COUNT()` |
